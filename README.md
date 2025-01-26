# cadastro-hotel
using System;
using System.Collections.Generic;
using System.Collections.Specialized;
using System.ComponentModel;
using System.ComponentModel.Design.Serialization;
using System.Linq;
using System.Runtime.InteropServices;
using System.Security.Cryptography;
using System.Text;
using System.Text.RegularExpressions;
using System.Threading.Tasks;

namespace praticando
{
    internal class Program
    {

        static int dias = 0;
       static int dia = 0, mes = 0, ano = 0;
      static  DateTime data1 = new DateTime(2025, 1, 25);
      static  DateTime data2 = new DateTime(2025, 2, 4);

        static int[] cadastroDias = new int[3];
        static string[] clientes = new string[3];
        static void Main(string[] args)
        {

            for(int i = 0; i < cadastroDias.Length; i++)
            {
                Console.Write("informe o seu nome: ");
                string nome = Console.ReadLine();
                Console.Clear();

                entrada();
                saida();


                if (data2 < data1)
                {
                    Console.WriteLine("erro");
                }
                else
                {
                    TimeSpan diferenca = data2 - data1;
                    cadastroDias[i] = diferenca.Days;
                    clientes[i] = nome;
                   // Console.WriteLine(nome + " esta cadastrado");
                    //Console.WriteLine("dias de hospedagem: " + diferenca.Days);


                }

            }
          for(int i = 0; i < clientes.Length; i++)
          {
                Console.WriteLine(clientes[i] + " esta cadastrado e ficara " + cadastroDias[i] + " dias no hotel");
          }
          

            Console.ReadLine();
        }
       static void entrada()
        {
            Console.WriteLine("data de entrada");
            Console.Write("diga seu dia de entrada no hotel: ");
            dia = int.Parse(Console.ReadLine());
            Console.Write("diga seu mes de entrada no hotel: ");
            mes = int.Parse(Console.ReadLine());
            Console.Write("diga seu ano de entrada no hotel: ");
            ano = int.Parse(Console.ReadLine());
            data1 = new DateTime(ano, mes, dia);
            Console.Clear();
        }
        static void saida()
        {
            Console.WriteLine("data de saida");
            Console.Write("diga seu dia de saida no hotel: ");
            dia = int.Parse(Console.ReadLine());
            Console.Write("diga seu mes de saida no hotel: ");
            mes = int.Parse(Console.ReadLine());
            Console.Write("diga seu ano de saida no hotel: ");
            ano = int.Parse(Console.ReadLine());
            data2 = new DateTime(ano, mes, dia);
            Console.Clear();
        }
      
    }
}
