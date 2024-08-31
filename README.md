# Felipe
// Página Inicial
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);

// App.js
import React from 'react';
import axios from 'axios';

function App() {
  const [apps, setApps] = React.useState([]);

  React.useEffect(() => {
    axios.get('/api/apps')
      .then(response => {
        setApps(response.data);
      })
      .catch(error => {
        console.error(error);
      });
  }, []);

  return (
    <div>
      <h1>Aplicativos Disponíveis</h1>
      <ul>
        {apps.map(app => (
          <li key={app.id}>
            <h2>{app.name}</h2>
            <p>{app.description}</p>
          </li>
        ))}
      </ul>
    </div>
  );
}

export default App;

// server.js
const express = require('express');
const app = express();
const port = 3000;

app.get('/api/apps', (req, res) => {
  // Retorna a lista de aplicativos do banco de dados
  res.json([
    { id: 1, name: 'Aplicativo 1', description: 'Descrição do Aplicativo 1' },
    { id: 2, name: 'Aplicativo 2', description: 'Descrição do Aplicativo 2' },
    // ...
  ]);
});

app.listen(port, () => {
  console.log(`Server started on port ${port}`);
});