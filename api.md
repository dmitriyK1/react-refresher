================================================================================
ES6
================================================================================

// Use default arguments instead of defaultProps for stateless components:
function ExpandableForm({ onExpand, expanded = false, children }) {}

================================================================================

componentWillMount() {
    // component not in the DOM yet
    // access only to state & props
}

componentDidMount() {
    // by this time we have access to a DOM element
    var domElement = ReactDOM.findDOMNode(this);
}

componentWillUnmount() {
    // do cleanup here
}

================================================================================

React.createClass

ReactDOM.render
ReactDOM.findDOMNode
ReactDOM.unmountComponentAtNode

getInitialState() {}

// state callback
this.setState({ visible: true }, () => alert('done') );

# нельзя вызывать setState в render: реакт
видит изменилось состояние - начинает перерисовывать компонент - видит что
изменилось состояние - начинает перерисовывать компонент...

getDefaultProps() {}

this.setState({})

this.replaceState( this.getInitialState() )

this.props.firstName
this.state.time
this.refs.input
this.refs.slider.refs.input                       // nested refs

<input value={this.state.value} onChange={this.onChange} />

onChange(e) {
    this.setState({ value: e.target.value });
}


<BButton>I <BHeart/> React</BButton>
<div>{ this.props.children }</div>


componentWillMount() {}
componentDidMount() {}
componentWillUnmount() {}

shouldComponentUpdate(nextProps, nextState, c) {
    return nextState.value % 2 === 0;
}

componentWillUpdate(nextProps, nextState) {}
componentDidUpdate(prevProps, prevState, rootNode) {}

propTypes: {

    txt: React.PropTypes.string.isRequired,

    optionalUnion: React.PropTypes.oneOfType([
        React.PropTypes.string,
        React.PropTypes.number,
        React.PropTypes.instanceOf(Message)
    ]),

    optionalObjectWithShape: React.PropTypes.shape({
        color: React.PropTypes.string,
        fontSize: React.PropTypes.number
    }),

    requiredAny: React.PropTypes.any.isRequired

}

render() {
    return <div data-rendered="true"></div>                   // append data- to show attribute in resulting html
}

// if/else usage in jsx
    return (<div>
        { true ? 'yes' : 'no' }
        { true && 777         }
    </div>)




var ReactMixin = {
    componentWillMount() { }
};

React.createClass({

    mixins: [ReactMixin],

    render() {},

    componentWillMount() {}
});





// dynamically generating elements
render() {
    return { this.state.items.map( item => <Element key={item.id} someData={item.value} /> ) }
}

var List = React.createClass({

    getInitialState() {

        return {
            people: [{ id:0, name: 'foo' }, { id:1, name: 'bar'},{ id: 3, name: 'baz' }]
        };

    },

    render() {
        return <section>
            { this.state.people.map(function(person) {
                return <ListItem key={person.id} data={person.name} />
            })
        }
        </section>
    }

});


// stateless component
var App = function() {
    return <div>this is a functional stateless component</div>;
}

ReactDOM.render( <App/>, app );
