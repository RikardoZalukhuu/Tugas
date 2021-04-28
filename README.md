import 'package:flutter/material.dart';
void main() => runApp(App());

class App extends StatelessWidget {
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter penyimpanan data',
      home: Scaffold(
        appBar: AppBar(
          title: Text('6SIA10'),
        ),
        body: Penduduk(),
      ),
    );
  }
}

class DataPenduduk{
  
  String namapenduduk;
  String Nik;
  String jkelamin;
  
  
  DataSiswa({ this.namapenduduk, this.Nik, this.jkelamin});
  
}

// class Penduduk
class Penduduk extends StatefulWidget {
  _MyappState createState() => _MyappState();
}

class _MyappState extends State<Siswa> {
  //deklarasi variabel
  final txtnamapenduduk = TextEditingController();
  final txtalamat = TextEditingController();
  final txthp = TextEditingController();
  

  List<Widget> data = [];

  onTambah() {
    setState(() {
      data.add(ListTile(
        leading: Text(txtalamat.text),
        title: Text(txtnamapenduduk.text),
        subtitle: Text(txtnik.text),
        trailing: Text(txtjkelamin.text),
      ));
      txtnamapenduduk.clear();
      txtnik.clear();
      txtjkelamin.clear();
      txtalamat.clear();
    });
  }

  Widget build(BuildContext context) {
    return ListView(
      children: <Widget>[
        new Container(
          padding: EdgeInsets.all(10.0),
          child: Column(
            mainAxisAlignment: MainAxisAlignment.spaceEvenly,
            children: <Widget>[
           
              TextField(
                controller: txtnamapenduduk,
                decoration: InputDecoration(hintText: 'Nama Penduduk'),
              ),
              TextField(
                controller: txtnik,
                decoration: InputDecoration(hintText: 'NIK'),
              ),
              TextField(
                controller: txtjkelamin,
                decoration: InputDecoration(hintText: 'jkelamin'),
              ),
               TextField(
                controller: txtalamat,
                decoration: InputDecoration(hintText: 'alamat'),
              ),
              Divider(height: 5.0),
              ElevatedButton(child: Text("Tambah"), onPressed: onTambah),
            ],
          ),
        ),
        new Column(
          children: data,
        )
      ],
    );
  }
}
