#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <string>
#include <map>
#include <unordered_map>

using namespace std;

class Elemento
{
    int id;
    string nome;
    float valor;

public:
    Elemento(int, float, string);

    float pegaValor()
    {
        return valor;
    }

    int pegaId()
    {
        return id;
    }

    string pegaNome()
    {
        return nome;
    }

    void insereValor(float v)
    {
        if (v >= 0)
        {
            valor = v;
        }
        else
        {
            printErro(0);
        }
    }

    void insereId(int i)
    {
        if (i > 0 || i < 6)
        {
            id = i;
        }
        else
        {
            printErro(1);
        }
    }

    void insereNome(string n)
    {
        int tamanho = strlen(n.c_str());
        if (tamanho > 0 && tamanho < 20)
        {
            nome = n;
        }
        else
        {
            printErro(2);
        }
    }

    void printErro(int tipoErro)
    {
        string erro;
        if (tipoErro == 0)
        {
            erro = "O valor do elemento  C) invC!lido.\n";
        }
        else if (tipoErro == 1)
        {
            erro = "O id do elemento possui quantidade de caracetre invC!lida.\n";
        }
        else
        {
            erro =
                "O nome do elemento possui quantidade de caractere invC!lida.\n";
        }
        printf("%s", erro.c_str());
    }
};

Elemento::Elemento(int i, float v, string n)
{
    insereId(i);
    insereValor(v);
    insereNome(n);
}

class Colecao
{
    string nome;
    map<int, Elemento> elementos;
    float valor;

public:
    Colecao(string, map<int, Elemento>, float);

    void insereNome(string n)
    {
        int tamanho = strlen(n.c_str());
        if (tamanho > 0 && tamanho < 20)
        {
            nome = n;
        }
        else
        {
            printErro(2);
        }
    }

    void insereElemento(Elemento e)
    {
        elementos.insert(make_pair(e.pegaId(), e));
    }

    void deletaElemento(int id)
    {
        elementos.erase(id);
    }

    Elemento pegaElemento(int id)
    {
        return elementos.find(id)->second;
    }

    map<int, Elemento> pegaTotalElementos()
    {
        return elementos;
    }

    string pegaNome()
    {
        return nome;
    }

    float pegaValorTotal()
    {
        float valorTotal = 0;
        for (auto e : elementos)
        {
            valorTotal += e.second.pegaValor();
        }
        return valorTotal;
    }

    void printErro(int tipoErro)
    {
        string erro;
        if (tipoErro == 0)
        {
            erro = "O valor do elemento  C) invC!lido.\n";
        }
        else if (tipoErro == 1)
        {
            erro = "O id do elemento possui quantidade de caracetre invC!lida.\n";
        }
        else
        {
            erro =
                "O nome do elemento possui quantidade de caractere invC!lida.\n";
        }
        printf("%s", erro.c_str());
    }
};

Colecao::Colecao(string n, map<int, Elemento> e, float v)
{
    insereNome(n);
}

int main()
{
    Elemento e(1, 4.4, "moeda");
    Elemento e2(2, 1.0, "oie");
    map<int, Elemento> elementos;
    Colecao c("album", elementos, 4.4);
    c.insereElemento(e);
    c.insereElemento(e2);

    printf("%f", c.pegaValorTotal());

    return 0;
}
