var number=random()
var pred
class NameForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {value: ''};

    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }

  handleChange(event) {
    this.setState({value: event.target.value});
    pred=this.state.value;
  }

  handleSubmit(event) {
    alert("You are submitting " + this.state.value);
    event.preventDefault();
    pred=this.state.value;
  
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <p>
          Gues the number:</p>
          <input
        type='text'
        name='number'
        onChange={this.handleChange}
      />
        
        <input type="submit" value="Check" />
       <p>{number}</p> 
        <p>{check(number,pred)} </p>
      </form>
    
    );
  }
}

ReactDOM.render(
  <NameForm />,
  document.getElementById('root')
);
function random() {
   var rand = String(Math.floor( Math.random()*1000)+1000) ;
  return <h1>{rand}</h1>;
}
function check (number,responce){
  return <h1>{responce}</h1>
}
