<<<<<<< HEAD
"# criptare.xor" 
"# criptare.xor" 
"# criptare.xor" 
"# criptare.xor" 
"# Guess-Game" 
"# Guess-Game" 
"# Dictionaty.demo" 
"# Dictionaty.demo" 
"# Tic-Tac-Toe" 
<<<<<<< HEAD
"# Tic-Tac-Toe" 
=======
>>>>>>> 7b4becc (first commit)
"# password_generator" 
"# password_generator" 
=======
Cod C++ criptare parole :


#include <iostream>
#include <fstream>
#include <string>
using namespace std;

struct Nod {
    char info;
    Nod *next, *prev;
};

void adauga(Nod *&prim, Nod *&ultim, char val) {
    Nod *nou = new Nod;
    nou->info = val;
    nou->next = nullptr;
    nou->prev = ultim;
    if (!prim) {
        prim = ultim = nou;
    } else {
        ultim->next = nou;
        ultim = nou;
    }
}

void afiseaza(Nod *prim) {
    for (Nod *p = prim; p; p = p->next)
        cout << p->info;
    cout << endl;
}

void cripteaza(Nod *prim, char cheie) {
    for (Nod *p = prim; p; p = p->next)
        p->info ^= cheie;
}

void elibereaza(Nod *&prim) {
    while (prim) {
        Nod *tmp = prim;
        prim = prim->next;
        delete tmp;
    }
}

int main() {
    int opt;
    char cheie = 'K';
    string linie;
    cout << "Apasati 0 pentru criptare si 1 pentru decriptare: ";
    cin >> opt;
    cin.ignore();
    ifstream f("lista.in");
    if (!f.is_open()) {
        cout << "Nu s-a putut deschide lista.in" << endl;
        return 1;
    }
    getline(f, linie);
    f.close();

  Nod *prim = nullptr, *ultim = nullptr;
  for (char c : linie)
        adauga(prim, ultim, c);

  if (opt == 0) {
        cout << "Text original:  ";
        afiseaza(prim);
        cripteaza(prim, cheie);
        cout << "Text criptat:   ";
        afiseaza(prim);
        ofstream g("lista.out");
        for (Nod *p = prim; p; p = p->next)
            g << p->info;
        g.close();
        cout << "Textul criptat a fost salvat in lista.out" << endl;
    } else if (opt == 1) {
        cout << "Text criptat:   ";
        afiseaza(prim);
        cripteaza(prim, cheie);
        cout << "Text decriptat: ";
        afiseaza(prim);
        ofstream g("lista.out");
        for (Nod *p = prim; p; p = p->next)
            g << p->info;
        g.close();
        cout << "Textul decriptat a fost salvat in lista.out" << endl;
    } else {
        cout << "Optiune invalida!" << endl;
    }

   elibereaza(prim);
    return 0;
}
>>>>>>> 3fe33802c9211d379d94c2d2c3425d0e0d8cab13
"# password_generator" 
"# password_generator" 
