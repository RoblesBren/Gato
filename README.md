# Gato
#include <iostream>
#include <stdlib.h>
#define A "\xCE"
#define B "\xCD"
#define V "\xBA"

using namespace std;

string jugador1();
string jugador2();

int main ()
{


    int error,empate=0,ganar=0,ganador;
    long int jugador=1;
    char l1='1',l2='2',l3='3',l4='4',l5='5',l6='6',l7='7',l8='8',l9='9',pos,marca,respuesta('y');
    string j1,j2;
    char g[3][3];
    g[0][0]=l1, g[0][1]=l2, g[0][2]=l3, g[1][0]=l4, g[1][1]=l5, g[1][2]=l6, g[2][0]=l7, g[2][1]=l8, g[2][2]=l9;

    jugador=1+rand()%1;
    j1=jugador1();
    j2=jugador2();

    cout<<j1<<": "<<"Usara 0"<<endl;
    cout<<j2<<": "<<"Usara X"<<endl;

    do                                                                                                    //Crea El Ciclo
    {
        error=1;

        cout<< "\t\t\t\tGATO"<< endl<<endl
            << "\t\t\t       " << V << "      " << V << "      " << endl
            << "\t\t\t   "  << g[0][0] << "   " << V << "   " <<g[0][1] << "  " << V << "  " <<g[0][2] << "   " << endl
            << "\t\t\t       " << V << "      " << V << "      " << endl
            << "\t\t\t  " << B << B << B << B << B << A << B << B << B << B << B << B << A << B << B << B << B << B << endl
            << "\t\t\t       " << V << "      " << V << "      " << endl
            << "\t\t\t   "  << g[1][0] << "   " << V << "  " << g[1][1]  << "   " << V << "  " << g[1][2]  << "   " << endl
            << "\t\t\t       " << V << "      " << V << "      " << endl
            << "\t\t\t  " << B << B << B << B << B << A << B << B << B << B << B << B << A << B << B << B << B << B << endl
            << "\t\t\t       " << V << "      " << V << "      " << endl
            << "\t\t\t   "  << g[2][0] << "   " << V << "  " << g[2][1]  << "   " << V << "  " << g[2][2]  << "   " << endl
            << "\t\t\t       " << V << "      " << V << "      " << endl << endl;

        if(jugador==1)                                                                                //Establece la marca del jugador
        {
            marca='X';
        }
        else
        {
            marca='O';
        }

        cout<<"EN QUE CASILLA DECEAS INSERTAR TU SIMBOLO JUGADOR"<<" "<<jugador<<endl;
        cin>>pos;

        if (pos=='1' && l1=='1')
        {
            g[0][0]=l1=marca;
        }
        else if (pos=='2' && l2=='2')
        {
            g[0][1]=l2=marca;
        }
        else if (pos=='3' && l3=='3')
        {
            g[0][2]=l3=marca;
        }
        else if (pos=='4' && l4=='4')
        {
            g[1][0]=l4=marca;
        }
        else if (pos=='5' && l5=='5')
        {
            g[1][1]=l5=marca;
        }
        else if (pos=='6' && l6=='6')
        {
            g[1][2]=l6=marca;
        }
        else if (pos=='7' && l7=='7')
        {
            g[2][0]=l7=marca;
        }
        else if (pos=='8' && l8=='8')
        {
            g[2][1]=l8=marca;
        }
        else if (pos=='9' && l9=='9')
        {
            g[2][2]=l9=marca;
        }
        else
        {
            cout<<"ESA CASILLA YA ESTA SIENDO USADA, O NO EXISTE, INTENTE DE NUEVO PORFAVOR\n";
            error=2;
        }

        if(l1=='X'||l1=='O')
        {
            if(l2==l1&&l3==l1 || l4==l1&&l7==l1)
            {
                ganar=1;
            }
        }

        if(l5=='X'||l5=='O')
        {
            if (l1 == l5 && l9 == l5 || l2 == l5 && l8 == l5 || l4 == l5 && l6 == l5 || l3 == l5 && l7 == l5)
            {
                ganar=1;
            }
        }

        if(l9=='X'||l9=='O')
        {
            if (l6 == l9 && l3 == l9 || l7 == l9 && l8 == l9)
            {
                ganar=1;
            }
        }

        if (l1 != '1' && l2 != '2' && l3 != '3' &&

                l4 != '4' && l5 != '5' && l6 != '6' &&

                l7 != '7' && l8 != '8' && l9 != '9')
        {
            empate=1;
        }

        if (ganar==1||empate==1)
        {

            if (ganar==1)
            {
                cout<<"FELICIDADES JUGADOR NO. "<<jugador<<" GANASTEEEE!\n\n"<<endl;
                cout<< "\t\t\t\tGATO"<< endl<<endl
                    << "\t\t\t       " << V << "      " << V << "      " << endl
                    << "\t\t\t   "  << g[0][0] << "   " << V << "   " <<g[0][1] << "  " << V << "  " <<g[0][2] << "   " << endl
                    << "\t\t\t       " << V << "      " << V << "      " << endl
                    << "\t\t\t  " << B << B << B << B << B << A << B << B << B << B << B << B << A << B << B << B << B << B << endl
                    << "\t\t\t       " << V << "      " << V << "      " << endl
                    << "\t\t\t   "  << g[1][0] << "   " << V << "  " << g[1][1]  << "   " << V << "  " << g[1][2]  << "   " << endl
                    << "\t\t\t       " << V << "      " << V << "      " << endl
                    << "\t\t\t  " << B << B << B << B << B << A << B << B << B << B << B << B << A << B << B << B << B << B << endl
                    << "\t\t\t       " << V << "      " << V << "      " << endl
                    << "\t\t\t   "  << g[2][0] << "   " << V << "  " << g[2][1]  << "   " << V << "  " << g[2][2]  << "   " << endl
                    << "\t\t\t       " << V << "      " << V << "      " << endl << endl;
            }

            if (empate==1)
            {
                cout<<"PEEEERDEDORES! EMPATE \n"<<endl;
                cout<< "\t\t\t\t"<< endl<<endl
                    << "\t\t\t       " << V << "      " << V << "      " << endl
                    << "\t\t\t   "  << g[0][0] << "   " << V << "   " <<g[0][1] << "  " << V << "  " <<g[0][2] << "   " << endl
                    << "\t\t\t       " << V << "      " << V << "      " << endl
                    << "\t\t\t  " << B << B << B << B << B << A << B << B << B << B << B << B << A << B << B << B << B << B << endl
                    << "\t\t\t       " << V << "      " << V << "      " << endl
                    << "\t\t\t   "  << g[1][0] << "   " << V << "  " << g[1][1]  << "   " << V << "  " << g[1][2]  << "   " << endl
                    << "\t\t\t       " << V << "      " << V << "      " << endl
                    << "\t\t\t  " << B << B << B << B << B << A << B << B << B << B << B << B << A << B << B << B << B << B << endl
                    << "\t\t\t       " << V << "      " << V << "      " << endl
                    << "\t\t\t   "  << g[2][0] << "   " << V << "  " << g[2][1]  << "   " << V << "  " << g[2][2]  << "   " << endl
                    << "\t\t\t       " << V << "      " << V << "      " << endl << endl;
            }

            cout<<"EL JUEGO SE A TERMINADO PRECIONE 'N/n' PARA SALIR, HASTA LUEGO...\n";
            cin>>respuesta;
        }

        if(error==1)
        {
            if (jugador==1)
            {
                jugador=2;
            }
            else
            {
                jugador=1;
            }
        }
    }
    while(respuesta!='n' && respuesta!='N');
}

string jugador1()
{
    string nm1;
    cout << "Cual es el nombre del jugador 1" << endl;
    getline(cin, nm1);
    return nm1;
}
string jugador2()
{
    string nm2;
    cout << "Cual es el nombre del jugador 2" << endl;
    getline(cin, nm2);
    return nm2;
}
