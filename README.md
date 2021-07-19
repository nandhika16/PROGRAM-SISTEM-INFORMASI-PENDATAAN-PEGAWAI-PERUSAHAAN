# PROGRAM-SISTEM-INFORMASI-PENDATAAN-PEGAWAI-PERUSAHAAN
Bahasa C++

#include <iostream>
#include <windows.h>
#include <conio.h>
#include <stdio.h>
#include <fstream>

using namespace std;

        
void selamat(){
		cout << "//===================================//";
		cout << "\n          IDENTITAS SAYA";
		cout << "\n//===================================//\n";
		cout << " Nama : Putu Nandhika Pratama Artana\n";
		cout << " NPM  : 19081010143\n";
		cout << " MK   : PEMROGRAMAN LANJUT KELAS D\n";
		
		cout << "\n\n||========================================================||\n";
		cout << "\n   PROGRAM SISTEM INFORMASI PENDATAAN PEGAWAI PERUSAHAAN\n";
		cout << "\n||========================================================||\n";  
		}
		
struct pegawai{
	string id;
	string nama;	//source code 15-19 berfungsi sebagai struct
	char JnsKelamin[10];
	string alamat;
};
int main(){
	int menu;
	int a, byk, yg;
	string mas, pass,user, cari;
	
	string name = "admin";
	string sandi = "admin12345";
	string* us = &name;	//untuk pointer
	string* sa = &sandi; //untuk pointer

	awal:
	selamat();
	cout << "\n  Menu Login Admin\n";
	
	cout << "\t Masukan username admin : "; cin>>user;
	cout << "\t Masukan password admin : "; cin>>pass;

	if(user == name && pass == sandi ){		//percabangan untuk memasuka user name dan password admin pada awal menu
											//Username Program : admin
											//Password program : admin12345
		satu:
		dua:
		system("CLS");	
		cout << "\t||===============================================||\n";
    	cout << "\t|	      PT.PERTAMINA SINGARAJA 	          |"<<endl;
    	cout << "\t||===============================================||\n";
    	cout << "\t    Pendataan Pegawai PT.PERTAMINA\t 	   "<<endl; //Menu 
   		
    	cout << "\t	1. Input Data Pegawai\t 		   "<<endl; // Inputan data 
    	cout << "\t	2. Data Semua Pegawai\t  		   "<<endl; // Inputan semua pegawai
    	cout << "\t	3. Keluar				   "<<endl; // Exit program
 
    
    cout << "\t Pilih Menu = "; cin>>menu; 
    	
    	if(menu==1){
    		cout<<"\n\t Masukan Jumlah Inputan Data Pegawai : ";
			cin>>byk;
			
			system("CLS");
			selamat();
			for(a=1; a<=byk; a++){
			cout<<"\n\tData Pegawai ke- "<<a<<endl;
			cin.ignore(100,'\n');//meriset cin yang pe.nama
	
			ofstream inalum;
			inalum.open("dataPT.txt", ios::app);
			pegawai pe;
			
			cout<<"\tMasukan ID Pegawai 	: ";
			getline(cin,pe.id);
			inalum<<endl<<pe.id;
			
			cout<<"\tMasukan Nama Pegawai 	: ";
			getline(cin,pe.nama);
			inalum<<endl<<pe.nama;
			
			cout<<"\tMasukan Alamat Pegawai 	: ";
			getline(cin,pe.alamat);
			inalum<<endl<<pe.alamat;
			
			cout<<"\tMasukan Jenis Kelamin Pegawai : ";
			cin>>pe.JnsKelamin;
			inalum<<endl<<pe.JnsKelamin;
			
			inalum.close();
	}
			system("CLS");
			
			cout<<"\n\tAPAKAH ANDA INGIN KEMBALI KE MENU UTAMA [y/t]: "; cin>>mas;
			if(mas == "y"){
				goto satu;
			}
			else{
				goto satu1;
			}
	}
		else if(menu==2){
			ifstream ina;
			string data;
			int i;
			system("CLS");
			selamat();
			ina.open("dataPT.txt");
			//while(!ina.eof()){
					getline(ina, data);
			for(i=1;!ina.eof(); i++){
			cout<<"\n";
			getline(ina, data);
			cout<<"Data Ke- "<< i;
			cout<<" 	ID 	: " + data<<endl;
			getline(ina, data);
			cout<<"		Nama 	: " + data<<endl;
			getline(ina, data);
			cout<<"		Alamat 	: " + data<<endl;
			getline(ina, data);
			cout<<"		Jns Kelamin 	: " + data<<endl;
		}
			
			cout<<"\t\tAPAKAH ANDA INGIN KEMBALI KE MENU UTAMA [y/n] : "; cin>>mas;
			system("CLS");
			if(mas == "y"){
				system("CLS");
				goto dua;
			}
			else{
				goto dua2;
			}
}
		else{
			satu1:
			dua2:
			cout << "\n//============================================//\n";
			cout << "\n   TERIMA KASIH SUDAH MENCOBA PROGRAM SAYA :)\n";
			cout << "\n//============================================//\n";
		}
}
	else{
		system("CLS");
		selamat();
		cout<<"\n\t USER NAME ATAU PASSWORD YANG ANDA MASUKAN SALAH \n";
		cout<<"\t Masukan User Name dan Password lagi [y/n] : "; cin>>mas;
		if(mas == "y"){
			system("CLS");
			goto awal;	
		}
		else{
			cout << "\n//============================================//\n";
			cout << "\n   TERIMA KASIH SUDAH MENCOBA PROGRAM SAYA :)\n";
			cout << "\n//============================================//\n";
		}
	}
}
