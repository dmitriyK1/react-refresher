
React.createClass

ReactDOM.render
ReactDOM.findDOMNode
ReactDOM.unmountComponentAtNode

getInitialState() {}

getDefaultProps() {}

this.setState({})

this.replaceState( this.getInitialState() )

this.props.firstName
this.state.time
this.refs.input
this.refs.slider.refs.input

<input value={this.state.value} onChange={this.onChange} />

onChange(e) {
    this.setState({ value: e.target.value });
}


<BButton>I <BHeart/> React</BButton>
<div>{ this.props.children }</div>


componentWillMount() {}
componentDidMount() {}
componentWillUnmount() {}

propTypes: {
    txt: React.PropTypes.string.isRequired
}
