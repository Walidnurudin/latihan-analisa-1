**1. Perbedaan Class Component dengan Functional Component.**
-
functional components lebih ringkas struktur kodenya. Hal ini sangat efektif karena kita tidak perlu mengetik terlalu panjang.

Namun ada perbedaan yang sangat besar antara class component dan function component, yaitu:

-   Functional component hanya bisa menggunakan  props  itu sebabnya function component disebut  stateless component  atau biasa digunakan juga sebagai  UI Component  (komponen yang menangani tampilan).
-   Sedangkan Class component dapat menggunakan  state  dan  props.

Contoh pembuatan class components:

```jsx
class App extends Component {
  render() {
    return (
      <div>
        <h1>Hello World</h1>
      </div>
    );
  }
}

```

Contoh pembuatan functional components:

```jsx
function App(){
  return(
    <div>
      <h1>Hello World</h1>
    </div>
  )
}

```




**2. Perbedaan State dan Props.**
-
- Apa itu **State**?

State merupakan data yang tersimpan dalam sebuah component. State bersifat private dan hanya relevan terhadap component itu sendiri. Berbeda dengan props yang valuenya dilempar dari component lain, state justru dapat menyimpan dan mengubah datanya sendiri dari dalam.  Dan state berbentuk seperti object.

contoh state :
```js
class Header extends Component {
  constructor() {
    super();
    this.state = {
      key: value // semua tipe-data
    };
  }

  render() {
    return (
      <div>
        <h1>{this.state.key}</h1>
      </div>
    );
  }
}
```

- apa itu  **Props**?

Props sendiri bisa dibilang adalah sebuah parameter default yang dimiliki oleh suatu component dimana ketika anda memanggil sebuah component.dan opsi ini untuk mempermudah developer mengelola parameter pada suatu component.

contoh props :
```jsx
const Navbar = ({ head }) => {
  return (
    <div>
      <p className="title">{head}</p>
    </div>
  );
};

export default Navbar;
```

Kita cukup membuat satu Navbar.  Navbar tersebut tinggal dipanggil di komponen-komponen yang kita inginkan. dan merubah nilai head sesuai dengan apa yang kita inginkan di setiap komponen.

Cara memanggilnya di App.js :

```jsx
import Navbar from "./Navbar";

class App extends Component {
  render() {
    return (
      <>
        <Navbar head="frontend" />
      </>
    );
  }
}

export default App;
```

**3. Perbedaan antara virtual DOM dengan real DOM**
-
- **Virtual DOM**

Pada virtual DOM kita terlebih dahulu membuat abstraksi DOM dalam bentuk virtual. Sehingga setiap perubahan terhadap struktur dokumen tidak terjadi secara langsung pada permukaan browser, akan tetapi terjadi di dalam memory. Sehingga proses menjadi lebih cepat. Dan hanya bagian yang butuh diubah saja yang kita render ulang.

- **real DOM**

Real DOM adalah suatu konsep atau cara logis untuk merepresentasikan struktur suatu dokumen dan bagaimana dokumen itu diakses serta dimodifikasi dalam bentuk pohon (tree) .

Dengan DOM, kita bisa mengakses, mengubah, mendelete suatu dokumen (atau tag) dalam HTML. Dan dalam dunia web, kita bisa melakukannya menggunakan Javascript dengan relatif mudah. Apalagi DOM selalu tersusun dalam bentuk tree.
