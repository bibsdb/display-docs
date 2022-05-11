# OS2Display documentation

This repository contains documentation for OS2Display.

## Changelog

See [changelog.md](changelog.md) for a list of changes.

## Roadmap

See [roadmap.md](roadmap.md) for a plan upcoming changes.

## Architecture

```mermaid
flowchart LR
    A[Admin] <-->B(API)
    B <--> C(Client)
```

## System description

| Component   | Description                                                                                                                                                                                                                                                                                                                                                            | Accessible by |
| ----------- |:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------| :-----------  |
| Slide | A slide is the visible content on a screen.                                                                                                                                                                                                                                                                                                                            | Admin, editor |
| Media | Media is either images or videos used as content for slides.                                                                                                                                                                                                                                                                                                           | Admin, editor |
| Theme | A theme has css, that can override the slide css.                                                                                                                                                                                                                                                                                                                      | Admin |
| Template | The template is how the slide looks, and which content is on the slide. Templates are imported from manually and developed outside the admin. Templates are accessible to choose on Slides.                                                                                                                                                                            | Admin, editor |
| Playlist | A playlist arranges the order of the slides, and the playlist is scheduled.                                                                                                                                                                                                                                                                                            | Admin, editor |
| Campaign | A campaign is a playlist, that takes precedence over all other playlists on the screen. If there a multiple campaigns, they are queued. A campaign is either directly attached to a screen, or attached to a group affecting the screens that are members of that group. If a campaign applies to a screen it fills the whole screen, not just a region of the screen. | Admin |
| Group | A group is a collection of screens.                                                                                                                                                                                                                                                                                                                                    | Admin |
| Layout | A layout consists of different regions, and each region can have a number of playlists connected. A layout is connected to a screen.                                                                                                                                                                                                                                   | Admin |
| Screen | A screen is connected to an actual screen, and has a layout with different playlists in.                                                                                                                                                                                                                                                                               | Admin |

```mermaid
flowchart LR
    Slide -->|1| D[Theme]
    Slide -->|1| E[Template]
    Slide -->|fa:fa-asterisk| F[Media]
```

```mermaid
flowchart LR
    Screen-->|fa:fa-asterisk|Layout
    Layout -->|fa:fa-asterisk|Playlist
    Playlist -->|fa:fa-asterisk|Slide

    Screen-->|fa:fa-asterisk|G[Campaign]
    G -->|fa:fa-asterisk|H[Slide]

    Screen-->|fa:fa-asterisk|Group

    Group-->|fa:fa-asterisk|L[Campaign]
    L -->|fa:fa-asterisk| M[Slide]

```
    
## API service

This is the main component of the system. All content is created/retrieved through api calls to the API service.
The API service is a [Symfony](https://symfony.com/) project built with [API Platform](https://api-platform.com/).
See [api-service.md](api-service.md) for further descriptions.
See [security.md](security.md) for further description of the security setup.

## Admin

This is where content, connections and screens are created and connected. 
[Go to description of admin elements](https://github.com/os2display/display-admin-client#system-description).
The admin is built with [React](https://reactjs.org/).
See [admin.md](admin.md) for further descriptions.

## Client 

This is the output screen where the content will be displayed.
The screen client is built with [React](https://reactjs.org/).
See [client.md](client.md) for further descriptions.

### Important nodes

Scheduling and campaigns will be activated when

  * their start time has been reached
  * (and) the current playlist has reached its end

to ensure proper transitions.

## Development setup

See [development.md](development.md) for a description of how to make changes to the project.

## Templates and Screen Layouts

See [templates.md](templates.md) for a description of how templates work and how to make new.
See [layouts.md](layouts.md) for a description of how layouts work and how to make new.

## Feeds

See [feeds.md](feeds.md) for a description of how feeds are set up.

## Hosting

See [hosting.md](hosting.md) for hosting instructions.
