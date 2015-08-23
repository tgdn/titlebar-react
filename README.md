# titlebar-react

Emulate OS X window title bar. Extracted from [mafintosh/playback](https://github.com/mafintosh/playback) and then forked from [kapetan/titlebar](https://github.com/kapetan/titlebar).

See the [live demo](http://kapetan.github.io/titlebar/demo/index.html) (Without React).

	npm install titlebar-react

```javascript
var React = require('react');
var Titlebar = require('titlebar-react');

var Component = React.createClass({

    handleClose: function(e) {
        console.log('closing');
    },
    handleMinimize: function(e) {
        console.log('minimize');
    },
    handleMaximize: function(e) {
        console.log('maximize');
    },
    handleFullScreen: function(e) {
        console.log('fullscreen');
    },

    render: function() {
        return (
            <div className="r-win">
                <Titlebar
                    draggable={true}
                    handleClose={this.handleClose}
                    handleMinimize={this.handleMinimize}
                    handleMaximize={this.handleMaximize}
                    handleFullScreen={this.handleFullScreen}>

                    /* any other React component here */
                </Titlebar>
            </div>
        );
    }

});

```

# Usage

~~The returned instance emits four events: `close`, `minimize`, `fullscreen` (each corresponding to one of the stoplight buttons) and `maximize` when double clicking on the title bar area, or holding down alt key and clicking `fullscreen`.~~

Instead of emitting four events, you get to define what each event will do by passing callbacks to this.props.

```javascript
<Titlebar
    handleClose={this.handleClose}
    handleMinimize={this.handleMinimize}
    handleMaximize={this.handleMaximize}
    handleFullScreen={this.handleFullScreen} />
```

## available props

- `draggable` (default `false`): Enable dragging.
- `handleClose`: called when close is clicked
- `handleMinimize`: called when minimized is clicked
- `handleMaximize`: called when maximize is clicked
- `handleFullScreen`: called when fullscreen is clicked
