# Library-Management-system.
#include <iostream>
#include <string.h>
#include <stdlib.h>
using namespace std;

class Library
{
public:
    int id;
    char name[100];
    char author[100];
    char student[100];
    int price;
    int pages;
    int status;
};

int main()
{
    Library lib[20];
    int input = 0;
    int count = 0;

    while (input != 5)
    {
        cout << "Enter 1 to input details like id, name,author,student,price,pages" << endl;
        cout << "Enter 2 to display details" << endl;
        cout << "Enter 3 to Issue book" << endl;
        cout << "Enter 4 to return book" << endl;
        cout << "Enter 5 to quit" << endl;
        cin >> input;

        switch (input)
        {
        case 1:
            cout << "Enter book id " << endl;
            cin >> lib[count].id;
            cout << "Enter book name " << endl;
            cin >> lib[count].name;
            cout << "Enter book author name " << endl;
            cin >> lib[count].author;
            cout << "Enter student name " << endl;
            cin >> lib[count].student;
            cout << "Enter book price " << endl;
            cin >> lib[count].price;
            cout << "Enter book pages " << endl;
            cin >> lib[count].pages;
            count++;
            break;

        case 2:
            for (int i = 0; i < count; i++)
            {
                cout << "Book id:" << lib[i].id << endl;
                cout << "Book name:" << lib[i].name << endl;
                cout << "Book author:" << lib[i].author << endl;
                cout << "Book Student :" << lib[i].student << endl;
                cout << "Book price:" << lib[i].price << endl;
                cout << "Book pages:" << lib[i].pages << endl;
            }
            break;
        case 3:
        {
            int id;
            cout << "Enter Book id to Issue:" << endl;
            cin >> id;
            for (int i = 0; i < count; i++)
            {
                if (lib[i].id == id)
                {
                    if (lib[i].status == 0)
                    {
                        lib[i].status = 1;
                        cout << "Book Issued Succesfully" << endl;
                    }
                    else
                    {
                        cout << "Book Already Issued" << endl;
                    }
                }
            }
        }
        break;
        case 4:
        {
            int id;
            cout << "Enter Book id to return:" << endl;
            cin >> id;

            for (int i = 0; i < count; i++)
            {
                if (lib[i].id == id)
                {
                    if (lib[i].status == 1)
                    {
                        lib[i].status = 0;
                        cout << "Book returned successfully" << endl;
                    }
                    else
                    {
                        cout << "Book was not Issued" << endl;
                    }
                }
            }
        }
        break;
        case 5:
            cout << "Existing program.." << endl;
            break;
        default:
            cout << "Invalid choice " << endl;
        }
    }
    return 0;
}
