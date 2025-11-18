# react-spa-protected-dashboard
# App.jsx
```
//
import { Navigate } from "react-router-dom";

export default function ProtectedRoute({ children }) {
  const isLoggedIn = localStorage.getItem("auth");
  return isLoggedIn ? children : <Navigate to="/login" />;
}
Home//
export default function Home() {
  return (
    <div>
      <h1>Home Page</h1>
      <p>Welcome to our SPA using React Router.</p>
    </div>
  );
}
//Login
import { useNavigate } from "react-router-dom";

export default function Login() {
  const navigate = useNavigate();

  const handleLogin = () => {
    localStorage.setItem("auth", "true");
    navigate("/dashboard");
  };

  return (
    <div>
      <h1>Login Page</h1>
      <button onClick={handleLogin}>Login</button>
    </div>
  );
}
// dashboard
import { Link, Outlet } from "react-router-dom";

export default function Dashboard() {
  return (
    <div>
      <h1>Dashboard</h1>

      <nav>
        <Link to="profile">Profile</Link> |{" "}
        <Link to="settings">Settings</Link> |{" "}
        <Link to="notifications">Notifications</Link>
      </nav>

      <hr />
      <Outlet /> {/* Renders nested routes */}
    </div>
  );
}
export default function Notifications() {
  return <h2>Notifications</h2>;
}
export default function Profile() {
  return <h2>Your Profile</h2>;
}
export default function Settings() {
  return <h2>Settings</h2>;
}
import logo from './logo.svg';
import './App.css';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App;

```
# Output
<img width="856" height="482" alt="image" src="https://github.com/user-attachments/assets/8fedfac3-d9a0-409a-a66a-82ce1c4324a7" />

<img width="911" height="486" alt="image" src="https://github.com/user-attachments/assets/427dd151-af32-4399-9f81-19795608dffe" />

<img width="1059" height="476" alt="image" src="https://github.com/user-attachments/assets/eb22d923-8bd9-4d97-8c94-108bf8d49ca1" />
# result
A functional SPA with proper navigation and authentication-based protected routes, implemented using modern React best practices and React Router v6. Users can only access dashboard content after logging in.
