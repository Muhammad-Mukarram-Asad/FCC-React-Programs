# FCC-React-Programs
Below are the some codes of the programs which I write during practice.

# Counter Program Code:  
class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0
    };
    // Change code below this line
this.increment = this.increment.bind(this);
this.decrement = this.decrement.bind(this);
this.reset = this.reset.bind(this);
    // Change code above this line
  }
  // Change code below this line
increment()
{
  this.setState(value => ({
    count : value.count+=1
  }))

}

decrement()
{
  this.setState(state => ({
    count: state.count-=1
  }))

}

reset()
{
  this.setState({
    count: 0
  })
}
  // Change code above this line
  render() {
    return (
      <div>
        <button className='inc' onClick={this.increment}>Increment!</button>
        <button className='dec' onClick={this.decrement}>Decrement!</button>
        <button className='reset' onClick={this.reset}>Reset</button>
        <h1>Current Count: {this.state.count}</h1>
      </div>
    );
  }
};

# setState Method:  
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      visibility: false
    };
    // Change code below this line
           this.toggleVisibility = this.toggleVisibility.bind(this);
    // Change code above this line
  }
  // Change code below this line

  toggleVisibility()
  {
    this.setState({
      visibility : !this.state.visibility
    })
    }
	// Another way to do this:
	
	toggleVisibility()
  {
    this.setState(state => ({
      visibility : !state.visibility
    }))
    }


  // Change code above this line
  render() {
    if (this.state.visibility) {
      return (
        <div>
          <button onClick={this.toggleVisibility}>Click Me</button>
          <h1>Now you see me!</h1>
        </div>
      );
    } else {
      return (
        <div>
          <button onClick={this.toggleVisibility}>Click Me</button>
        </div>
      );
    }
  }
}

# Controlled Input (setState Program):
class ControlledInput extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      input: ''
    };
    // Change code below this line
this.handleChange = this.handleChange.bind(this);
    // Change code above this line
  }
  // Change code below this line
handleChange(event)
{
  this.setState({
      input: event.target.value
  })
  
}
  // Change code above this line
  render() {
    return (
      <div>
        { /* Change code below this line */}
        <input type="text" value={this.state.input} onChange={this.handleChange} />

        { /* Change code above this line */}
        <h4>Controlled Input:</h4>
        <p>{this.state.input}</p>
      </div>
    );
  }
};

# Form Controlled in React:  
class MyForm extends React.Component {  
  constructor(props) {  
    super(props);  
    this.state = {
      input: '',
      submit: ''
    };
    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }  
  
  handleChange(event) {
    this.setState({
      input: event.target.value
    });
  }  
                         
  handleSubmit(event) {
    // Change code below this line
    event.preventDefault();
this.setState({
      submit: this.state.input
    });
    // Change code above this line
  }  
  
  render() {  
    return (  
      <div>  
	
        <form onSubmit={this.handleSubmit}>  
		
          {/* Change code below this line */}  
	  <input type="text" value={this.state.input} onChange = {this.handleChange} />  
          {/* Change code above this line */}  
          <button type='submit'>Submit!</button> 
        </form>  
	
        {/* Change code below this line */}  
	<h1>{this.state.submit}</h1>  
	
        {/* Change code above this line */}  
      </div>
    );
  }
}
