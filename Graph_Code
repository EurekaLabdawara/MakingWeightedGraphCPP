#include <iostream>

using namespace std;

struct TNode{
	char name;
	
	TNode *next1;
	int weight1;
	
	TNode *next2;
	int weight2;
	
	TNode *next3;
	int weight3;
};

TNode *start, *cari, *baru;
char nama, to, from;
int pil,berat;

bool startisEmpty(){
	if(start==NULL){
		return true;
	}
	return false;
}

void showallroute(TNode *p){
	if (p!=NULL)
	{
		cout<<p->name<<" ";
		if(p->next1 and p->weight1!=0)
		{
			cout<<p->weight1<<" ";
			showallroute(p->next1);
		}
		if(p->next2 and p->weight2!=0)
		{
			cout<<endl;
			cout<<p->name<<" "<<p->weight2<<" ";
			showallroute(p->next2);
		}
		if(p->next3 and p->weight3!=0)
		{
			cout<<endl;
			cout<<p->name<<" "<<p->weight3<<" ";
			showallroute(p->next3);
		}
	}
	else{
	cout<<endl;
	return;	
	}
}

void searchNode(TNode *p){
	if(p->name!=nama and p!=NULL){
		if(p->next1)
		searchNode(p->next1);
		if(p->next2)
		searchNode(p->next2);
		if(p->next3)
		searchNode(p->next3);
	}
	else if(p->name==nama){
		cari=p;
	}
}

int searchpathNULL(TNode *p){
	if(cari->next1==NULL){
		return 1;
	}
	else if(cari->next2==NULL){
		return 2;
	}
	else if(cari->next3==NULL){
		return 3;
	}
	else{
		return 0;
	}
}

void connectdari(char from,int berat){
	nama=from;
	searchNode(start);
	switch(searchpathNULL(cari)){
		case 1:
			cari->next1=baru;
			cari->weight1=berat;
		break;
		
		case 2:
			cari->next2=baru;
			cari->weight2=berat;
		break;
		
		case 3:
			cari->next3=baru;
			cari->weight3=berat;
		break;
		case 0:
			cout<<"Alamat yang dituju sudah terisi penuh!"<<endl;
		break;
	}
}

void connectmenuju(char to, int berat){
	nama=to;
	searchNode(start);
	if(baru->next1==NULL){
			baru->next1=cari;
			baru->weight1=berat;
	}
	else if(baru->next2==NULL){
			baru->next2=cari;
			baru->weight2=berat;
	}
	else if(baru->next3==NULL){
			baru->next3=cari;
			baru->weight3=berat;
	}else{
			cout<<"Alamat yang dituju sudah terisi penuh!"<<endl;
	}
}

void garis(){
	cout<<"==============================="<<endl;
}

void insertNewNode(char nama){
	int pilsub;
	baru= new TNode;
	baru->name=nama;
	baru->next1=NULL;
	baru->next2=NULL;
	baru->next3=NULL;
	baru->weight1=0;
	baru->weight2=0;
	baru->weight3=0;
	do{
		garis();
		cout<<"1. Dihubungkan dari"<<endl;
		cout<<"2. Menghubungkan ke"<<endl;
		cout<<"0. Kembali ke menu utama"<<endl;
		garis();
		cout<<"Masukan pilihan anda: ";cin>>pilsub;
		switch(pilsub){
			case 1:
				if(start==NULL){
				cout<<"Belum ada data lain!"<<endl;	
				}
				else{
				cout<<"Masukan nama Node yang menuju "<<nama<<" : ";cin>>from;
				cout<<"Dengan cost: ";cin>>berat;
				connectdari(from,berat);
				}
			break;
			
			case 2:
				if(start==NULL){
				cout<<"Belum ada data lain!"<<endl;	
				}
				else{
				cout<<"Masukan nama Node yang dituju : ";cin>>to;
				cout<<"Dengan cost: ";cin>>berat;
				connectmenuju(to,berat);
				}
			break;
			
			case 0:
				pilsub=0;
			break;
		}
	}while(pilsub!=0);
	if(start==NULL){
		start=baru;
	}
}

int main(){
	char pilkeluar='N';
	while(pilkeluar=='N' or pilkeluar=='n'){
	cout<<"Program Weighted Graph Sederhana"<<endl;
	garis();
	cout<<"1. Tambahkan Node Baru"<<endl;
	cout<<"2. Tampilkan Semua Rute"<<endl;
	cout<<"0. Exit"<<endl;
	garis();
	cout<<"Masukan pilihan anda: ";cin>>pil;
	switch (pil){
		
		case 1:
		cout<<"Masukan nama Node : ";cin>>nama;
		insertNewNode(nama);
		break;
		
		case 2:
			if(start==NULL){
				cout<<"Data masih kosong!"<<endl;
			}
			else{
			showallroute(start);
			cout<<endl;	
			}
		break;
		
		case 3:
			cin>>nama;
			searchNode(start);
			cout<<cari->name;
		break;
		case 0:
			cout<<"Anda yakin? [Y/N]"<<endl;
			cin>>pilkeluar;
		break;
		}
	system("pause");
	system("cls");
	}
	exit(0);
}
