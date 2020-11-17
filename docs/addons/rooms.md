
[< Go back to Home](../index.md)

### [Addons](index.md)
* [Rooms addons](rooms.md)
* [More page addons](more_page.md)
* [Persons addons](persons.md)
* [House information addons](house_information.md)

---

# Rooms addons

With rooms addons you can add own functionality to rooms. You can add a own button on a room page which links to a custom page. It can also parse some data to that view. 

## Rooms page addons information

I advise you to create a folder inside `dwains-dashboard/addons/rooms/` with the name of the addon (for example statistics) inside that folder create a file called `page.yaml` and inside that file your lovelace card(s) and use that path as the path for the addon.

A good example is to checkout the `hello-room` addon in `dwains-dashboard/addons/rooms/hello-room/page.yaml` to re-use or inspire you. 

| Name | Type   | Default          | Example                                                                                                               | Description                       |
|------|--------|------------------|-----------------------------------------------------------------------------------------------------------------------|-----------------------------------|
| name | string | Required         | Hello room                                                                                                            | The name of the addon             |
| icon | string | fas:puzzle-piece | fas:chart-area                                                                                                        | The icon of the addon             |
| show_header | boolean | Optional | `'false'` (default: true) | If you want to hide the top header on the addon page |
| path | string | Required         | `dwains-dashboard/addons/rooms/hello-room/page.yaml`                                                              | The path to the page of the addon |
| button_path | string | Optional  | `dwains-dashboard/addons/rooms/hello-room/button.yaml`                                                              | The path to the button of the addon |
| data | object | Not required     | See example below | Data you wanna parse to the addon |

## Rooms addon example 

This is for the `config/rooms.yaml` file.

```YAML
rooms:
  - name: Hallway
    ...your existing strings...
    addons:
      - name: Hello room
        icon: fas:puzzle-piece
        path: 'dwains-dashboard/addons/rooms/hello-room/page.yaml'
        button_path: 'dwains-dashboard/addons/rooms/hello-room/button.yaml'
        data:
          some_data: 'This is some data parsed.'
          some_other_data: 'and some other data.'
          entity: vacuum.roborock
```    
