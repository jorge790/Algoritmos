practico 1
#include "stdafx.h"
	#include <iostream>
	#include "conio.h"
	#include "math.h"
	#include "stdlib.h"
	#define PI 3.1416
	
	using namespace std;
	float volumen(float r);
	float ganancia(float x,int n);
	int suma(int n);
	int sumdigitos(int n);
	float cambiobaseDec(float b,int n);
	int invertir(int n);     
	int chaupares (int n);
	
	void main()
	{int n,opcion,h,m,s,hr,n1,n2,res,c,i,d;
	float vol,r,z,x,base;
		do{
			cout<<endl<<endl<<"   PRACTICO 1  ";
			cout<<endl<<endl<<"--------MENU---------";
			cout<<endl<<"1.-Hallar el volumen de la circunferencia.";
			cout<<endl<<"2.-Un trabajador gana por horas trabajadas X Bs. si trabaja N horas en un mes cuanto es el 80% de su ganacia en un mes";
			cout<<endl<<"3.-introducir hrs,minutos y seg y hacerlo en formato de 12 hrs.";
			cout<<endl<<"4.-suma,resta y multiplicacion.";
			cout<<endl<<"5.-Hallar la suma de los primeros N numeros naturales";
			cout<<endl<<"6.-Mostrar los primero N terminos de la serie siguiente 2,6,10,14..";
			cout<<endl<<"7.-Hallar la suma de los digitos de un  numero.";
			cout<<endl<<"8.-Cambio de un numero en base N a base decimal";
			cout<<endl<<"9.-Introducir un numero y de ese número eliminar todos los pares:";
			cout<<endl<<"10.-Invertir un numero natural";
			cout<<endl<<"0.- salir";
			cout<<endl<<"seleccione una opcion: ";
			cin>> opcion;
			system("cls");
			switch (opcion){
				case 1:cout<<"ingrese el radio:";
						cin>>r;
						vol = volumen(r);
						cout<<"el volumen de la circunferencia es:"<<vol;
						break;
				case 2:cout<<"ingrese la ganancia por hora trabajada:";
					cin>>x;
					cout<<"ingrese la cantidad de horas trabajaas al mes;";
					cin>>n;
					z = 0.8*ganancia(x, n);
					cout<<"el 80% de la ganacia es:"<<z;
					break;
				case 3: do{
							cout<<"introducir las horas: ";
							cin>>h;
						  }while(h>24);
	
						do{
							cout<<"intoducir los minutos:";
							cin>>m;
						  }while(m>=60);
	
						do{
							cout<<"intoducir los segundos:";
							cin>>s;
						  }while(s>=60);
	
							if(h ==24)
								{h = 0;
								}
							if ( h >12)
								{ hr = h-12;
								  cout<<"son las "<<hr<<":"<<m<<":"<<s<<"p.m.";
								}
							else
								{cout<<"son las "<<h<<":"<<m<<":"<<s<<"a.m.";
								}
							break;
				case 4:
					cout<<"introduzca el primer valor: ";
					cin>> n1;
					cout<<"introduzca el segundo valor: ";
					cin>>n2;
					s = n1 + n2;
					res = n1-n2;
					m = n1*n2;
					cout<<"la suma de "<<n1<<" y "<<n2<<" es: "<<s<<endl;
					cout<<"la resta de "<<n1<<" y "<<n2<<" es: "<<res<<endl;
					cout<<"la multiplicacion de "<<n1<<" y "<<n2<<" es: "<<m<<endl;
					break;
				case 5:
					cout<<"ingrese el numero:";
					cin>> n;
					s = suma(n);
					cout<<"la suma de los primeros "<<n<<" numeros naturales es: "<<s;
					break;
				case 6:
					cout<<"ingrese la cantidad de terminos q requiere de la serie: ";
					cin>>n;
					c = 2;
					for (i=1; i<=n ;i++)
					{	cout<<c<<",";
						c = c + 4;
					}
					break;
				case 7:
					cout<<"ingrese el numero: ";
					cin>>n;
					s = sumdigitos(n);
					cout<<"la suma de los digitos es: "<<s;
					break;
				case 8:cout<<" ingrese la base del numero a convertir: ";
					cin>> base;
					cout<<"ingrese el numero a convertir: ";
					cin>> n;
					cout<<" el numero en base 10 es :"<<cambiobaseDec(base,n);
					break;
				case 9:cout<<"ingrese un numero: ";
					cin>>n;
					n1 = chaupares(n);
					n2 = invertir(n1);
					cout<<"el numero sin digitos pares es: "<<n2;
					break;
				case 10:
					cout<<"ingrese el numero: ";
					cin>>n;
					n1 = invertir(n);
					cout<<"el numero invertido es: "<<n1;
					break;
				case 0:
					cout<<"salir";
					break;
				default:cout<<"error";
					break;
				}
			getch();
			}while (opcion != 0);
		}
	
	
	
	
	
	
	
	float volumen(float r)
	{float vo;
		vo= (4*PI*r*r*r)/3;
		;
		return vo;
	}
	
	float ganancia(float x,int n)
	{float r;
	r=x*n;
	return r;
	}  
	
	
	int suma(int n)
	{int sum = 0, i;
		for ( i=1;i<=n;i++)
			sum= sum +i;
		return sum;
	}
	
	int sumdigitos(int n)
	{int d,sum;
	sum = 0;
	while( n>0)
		{ d = n%10;
		  n =n/10;
		  sum = sum + d;
		}
		  return sum;
	}
	
	float cambiobaseDec(float b,int n)
	{int i=0,r,a,s=0;
		while (n > 0)
		{r = n % 10;
		n = n/10;
		a = r*pow(b,i);
		s = s+a;
		i++;
		}
		return s;
	}
	
	
	int chaupares (int n)
	{int d,imp = 0;
		while(n > 0)
		{d = n%10;
		 n = n/10;
		 if(d%2 != 0)
		  imp = imp *10 + d;
		}
		return imp;
	}
	
	int invertir(int n)
	{int r,ninv;
	ninv = 0;
		while (n>0)
		{r = n %10;
		 n = n/10;
		 ninv = ninv *10 + r;
		}
		return ninv;
	}



