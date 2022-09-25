#include<iostream>
using namespace std;
class ArrayList{
	private:
		int array[100];
		int last;
	public:
		ArrayList();
		int length();
		bool isFull();
		bool isEmpty();
		void insert(int x, int pos);
		void remove(int pos);
		void append(int x);
		void print();
};
ArrayList::ArrayList(){
	last=-1;	
}
int ArrayList::length(){
	return last+1;
}
// empty 
bool ArrayList::isEmpty(){
	bool empty;
	for(int i=0;i<=last;i++)
		if (last==99)
		{
			empty= false;
			break;
		}
		else
			empty = true;
}
// full
bool ArrayList::isFull(){
	bool full;
	for(int i=0;i<=last;i++)
		if (last==99)
		{
			full= true;
			break;
		}
		else
			full = false;
}
// insert
void ArrayList::insert(int x,int pos){
	for(int i=last;i>=pos;i--){
		array[i+1]=array[i];
	}
	array[pos]=x;
	last++;
}
// remove
void ArrayList::remove(int pos){
	for(int i=pos;i<last;i++){
		array[i]=array[i+1];
	}
	last--;	
}
// append
void ArrayList::append(int x){
	array[last+1]=x;
	last=last+1;
}
// print
void ArrayList::print(){
	for(int i=0;i<=last;i++)
		cout<<"a["<<i<<"] = "<<array[i]<<"\t";
}
int main(){
	ArrayList l;
	cout<<"do dai mang: "<<l.length()<<endl;
	l.append(5);
	l.print();
	cout<<"\n";
	l.append(10);
	l.print();
	cout<<"\n";
	l.insert(7,2);
	l.print();
	cout<<"\n";
	l.insert(22,1);
	l.print();
	cout<<"\n";
	l.remove(2);
	l.print();
	cout<<"\n";
	l.remove(1);
	l.print();	
;}
