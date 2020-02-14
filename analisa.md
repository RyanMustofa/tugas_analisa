EVALUASI ANALISA

>Class Component

**Class component** memiliki State dan dapat menjalankan state dengan tepat dan cepat . class component itu merupakan virtual dom dan react component harus menggunakan render() untuk merender state , class component itu me load aplikasi sedikit lebih lama dari pada functional component karena memuat data lebih banyak pasti akan lebih berat kelebihan class component adalah membuat react menjadi lebih dinamis dan juga lebih efisie karena state dapat di update , dapat memuat banyak data yang bersifat relatif . contoh

    class App extends React.Component{
    	    constructor(){
    	    super();
    	    this.state = { key : value }
		}
		render(){
			return(
				<div>
					<h1>{this.state.key}</h1>
				</div>
			)
		}
    }

>Functional Component

**Functional Component** adalah component yang hanya memiliki props , karena state tidak mendukung untuk functional component . Functional component hanya bisa menggunakan props itu sebabnya function component disebut stateless component atau biasa digunakan juga sebagai UI Component (komponen yang menangani tampilan), kelebihan functional itu adalah memuat component dengan cepat karena lebih ringan dari pada class, functional itu tanpa render() karena functional meruapakan real dom
contoh menggunakan function es 5 ke bawah
```
jsx
function App(){
  return(
    <div>
      <h1>Hello World</h1>
    </div>
  )
}
```
contoh penggunaan function es 6
```
jsx
const App = () => {
  return(
    <div>
      <h1>hello world</h1>
    </div>
  )
}
```
>Props

**Props** merupakan property dari react , jika kita belajar html kita tau bahwa di html terdapat property atau atribut , sedangkan di react fungsinya itu sama tapi di react biasanya digunakan untuk melempar component biasanya prop0s dapat berupa berbagai tipe bahkan bisa berupa state props biasa digunakan untuk fetch data yang sangat banyak kelebihan props yaitu dapat digunakan maping data di functional component , mengatur style ing dengan mudah , lebih terlihat rapi, Prop itu read-only, Prop umumnya digunakan untuk komunikasi data component dari _parent_ komponent ke _child_ component. . Jika componentnya dalam bentuk class maka prop ini property dari class nya yang di akses melalui keyword ‘_this’_
>State

**State** merupakan tempat penyimpanan data di react ,state bisa dibilang penyimpanan data yang bersifat relatif maksudnya jika browser di close atau di tutup maka state akan hilang / di destroy karena state bersifat statis. state juga merupakan data private dari sebuah component, jika state itu berada di component yang digunakan maka state itu tidak bisa digunakan di component lain karena state hanya bisa di gunakan di component tersebut , state juga tidak bisa digunakan di functional component  , didalam state juga terdapat ***inisial state*** yaitu state harus berada di dalam constructor() , ***Update State*** untuk merubah state digunakan this.setState , *****Read Component State***** untuk mendeklarasikan state dengan menggunakan this.state.key
>Virtual Dom

**Virtual Dom** Dari pada langsung bekerja dengan DOM secara langsung pada browser, pada virtual DOM kita terlebih dahulu membuat abstraksi DOM dalam bentuk virtual. Sehingga setiap perubahan terhadap struktur dokumen tidak terjadi secara langsung pada permukaan browser, akan tetapi terjadi di dalam memory. Sehingga proses menjadi lebih cepat.Setelah modifikasi pada Virtual DOM selesai, kita lakukan proses  _differing_  untuk membedakan antara struktur tree yang telah dirender sebelumnya pada browser dengan virtual tree yang sudah dibuat. Sehingga akan menghasilkan bagian-bagian yang ‘kotor’ alias berbeda. Dan  hanya bagian yang butuh diubah saja yang kita render ulang.Proses ini tentu jauh lebih efektif dan lebih cepat dari pada jika kita harus bekerja secara langsung pada DOM yang asli
>Real Dom

**Real Dom**  biasanya hanya mengambil data dari elemen html , karenanya virtual dom lebih baik dari real dom ,pada umumnya real dom dapat mengubah styleing seperti warna , backgrounds ,  font color , dan lain lain . bahkan real dom ini dapat berupa  tulisan langsung pada tag html contoh 

    ...
	    <div id="root"></div>
	    <script>
		    get.elementById('root').innerHTML = "hello world"
	    </script>
    ...
dan dapat juga menambah color yaitu
 

       ...
    	    <div id="root"></div>
    	    <script>
    		    get.elementById('root').style.background = "red"
    	    </script>
        ...

real dom biasa digunakan di public react sebagai saran jangan pakai realdom di react karena kurang evektif karena jika merubah state harus reload browser . lebih baik gunakan virtual dom
