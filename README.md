# Import React

```typescript
import * as React from "react";
import * as ReactDOM from "react-dom";
```

# Functional Component

```typescript
type AppProps = {
  message: string;
};

const App = ({ message }: AppProps) => <div>{message}</div>;
const App = ({ message }: AppProps): JSX.Element => <div>{message}</div>;

// NOT RECOMMEND!
const App = ({ message }): React.FC<AppProps> => <div>{message}</div>;
```

# useRef

```typescript
const ref1 = React.useRef<HTMLElement>(null); // => For no edit ref1.current
const ref2 = React.useRef(); // => For edit ref2.current
```

# useState

```typescript
const [user, setUser] = React.useState<IUser | null>(null);
const [user, setUser] = React.useState<IUser>({} as IUser); // => Using type assertion
```

# useReducer

```typescript
const initalState = { count: 0 };
type Action =
  | {
      type: "increment";
      payload: number;
    }
  | { type: "decrement"; payload: number };

function reducer = (state: typeof initialState, action: Action) => {
    switch (action.type) {
        case "increment":
            return {count: state.count + action.payload};
        default:
            return state;
    }
}
```

# Basic Types

```typescript
// A dict object with any number of properties of the same type
type AppProps = {
  dict1: { [key: string]: MyType };
  dict2: Record<string, MyType>;
  onClick: () => void;
  onClick: (event: React.MouseEvent<HTMLButtonElement>) => void;
  children: React.ReactNode;
  style?: React.CSSProperties;
  onChange: React.FormEventHandler<HTMLInputElement>
};
```

# Form and Event
```typescript
class App extend React.Component<Props, State>{
  state = {
    text: ""
  }

  onChange = (e: React.FormEvent<HTMLInputElement>): void => {}
  onChange: React.ChangeEventHandler<HTMLInputElement> = e => {}
}
```