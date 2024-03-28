#include <iostream>
#include <iomanip>
#include <stdlib.h>
#include <ctime>
using namespace std;

int main()
{
    srand(time(NULL));
    double w0 = (rand() % 10 + 1) / 20.0,
        w1 = (rand() % 10 + 1) / 20.0,
        w2 = (rand() % 10 + 1) / 20.0,
        w3 = (rand() % 10 + 1) / 20.0,
        n = 0.02;

    int X[][3] = {
        { 0, 0, 0},
        { 0, 0, 1 },
        { 0, 1, 0},
        { 0, 1, 1 },
        { 1, 0, 0 },
        { 1, 0, 1 },
        { 1, 1, 0 },
        { 1, 1, 1}
    };
    int T[] = { 1, 1, 1, 1, 0, 1, 1, 1 };

    cout << "n: " << n << endl;
    bool flag;
    int count = 0;
    do
    {
        count++;
        cout << "Iteration N" << count << endl;
        flag = false;
        double teta = 0.5;
        cout << setw(6) << "w0" << setw(6) << "w1" << setw(6) << "w2" << setw(6) << "w3" << setw(7) << "theta" << setw(6) << "x0" << setw(6) << "x1" << setw(6) << "x2" << setw(6) << "x3" << setw(6) << "a" << setw(6) <<
            "Y" << setw(6) << "T" << setw(12) << "n(T - Y)" << setw(6) << "dw0" << setw(6) << "dw1" << setw(6) << "dw2" << setw(5) << "dw3" << setw(8) << "dtheta" << endl;
        for (int i = 0; i < 8; i++)
        {
            int Y = 0;
            double a = w1 * X[i][0] + w2 * X[i][1] + w3 * X[i][2] + w0;

            if (a > teta)
                Y = 1;

            double d;
            if (Y == T[i])
                d = 0;
            else
            {
                d = n * (T[i] - Y);
                flag = true;
            }
            cout << setprecision(3) << setw(6) << w0 << setw(6) << w1 << setw(6) << w2 << setw(6) << w3 << setw(7) << teta << setw(6) << 1 << setw(6) << X[i][0] << setw(6) << X[i][1] << setw(6) << X[i][2]
                << setw(7) << a << setw(5) << Y << setw(6) << T[i] << setw(9) << d << setw(9) << d << setw(6) << d * X[i][0] << setw(6) << d * X[i][1] << setw(5) << d * X[i][2] << setw(7) << d * teta << endl;
            w1 = w1 + d * X[i][0];
            w2 = w2 + d * X[i][1];
            w3 = w3 + d * X[i][2];
            w0 = w0 + d;
            teta = teta + d * teta;
        }
        cout << endl;
    } while (flag);
}





