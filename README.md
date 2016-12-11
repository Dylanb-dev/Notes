# Notes
Notes on Programming Concepts



## Actions in containers, for components(stateless) use:

```jsx

  Component = props => {
    return (
      <input
        className={props.className}
        id={props.id}
        placeholder={props.placeholder}
        onBlur={this._save}
        onChange={this._onChange}
        autoFocus={true}
      />
    );
  };
  
  const _save = () => {
    this.props.onSave(this.state.value);
    this.setState({
      value: ''
    });
  };

  const _onChange = (event) => {
    this.setState({
      value: event.target.value
    });
  };
```

## Use stateless components whenever possible (const) eg:
```jsx
const LatestPostsComponent = props => {
  const postPreviews = renderPostPreviews(props.posts);

  return (
    <section>
      <div><h1>Latest posts</h1></div>
      <div>
        { postPreviews }
      </div>
    </section>
  );
};

const renderPostPreviews = posts => (
  posts.map(post => this.renderPostPreview(post))
);

const renderPostPreview = post => (
  <article>
    <h3><a href={`/post/${post.slug}`}>{post.title}</a></h3>
    <time pubdate><em>{post.posted}</em></time>
    <div>
      <span>{post.blurb}</span>
      <a href={`/post/${post.slug}`}>Read more...</a>
    </div>
  </article>
);
```
## Use proptypes whenever possible eg:

```jsx
const ListOfNumbers = props => (
  <ol className={props.className}>
    {
      props.numbers.map(number => (
        <li>{number}</li>)
      )
    }
  </ol>
);

ListOfNumbers.propTypes = {
  className: React.PropTypes.string.isRequired,
  numbers: React.PropTypes.arrayOf(React.PropTypes.number)
};
```
