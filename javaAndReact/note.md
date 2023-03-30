 + **React ve jps**

**.jpx** aslında bir javascript excetion nudur.Sadwcw bir tane parent element dönebilir.Genel olarak biz div döneriz.
**{}** toplama değişken ve fonksş-iyonlarda köşeli parantez kullanılmalı

- **Render İşlemi** kullanıcı doğrı ise değil ise
```JavaScript
import React from 'react';
import './App.css';


const name = "sefa"
const surName = "demirtaş"
const isLoggedIn = true;
function App(){
  return(
    <div>
      <h1>{isLoggedIn 
      ? `Benimadım ${name} , soyadım ${surName}`
      : `Giriş Yapmadınız..`}</h1>
    </div>
  )
}

export default App

```

