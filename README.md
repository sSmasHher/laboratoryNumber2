# laboratoryNumber2

/***************************
* Автор: Полудинцев Никита *
* Вариант: 23              *
* Название: Лаб 2          *
***************************/

#include <iostream>
#include <cmath>
#include <iomanip>

using namespace std;

int main() {

    float I, a, b, pi, mu_0, postoyannaya_chast, koeff;
    I = 5.0;
    a = 3.5;
    b = 2.0;
    pi = 3.1415926;

    mu_0 = 4 * pi * 0.000000001;

    postoyannaya_chast = (100000000 / (2 * pi)) * mu_0 * I * a;

    koeff = postoyannaya_chast * 2;

    float s_mm[9] = { 2, 4, 6, 8, 10, 20, 30, 40, 50 };

    cout << "S (mm)" << "     " << "F (Vb)" << endl;
    cout << "------------------" << endl;

    for (int i = 0; i < 9; i = i + 1) {

        float s, otnoshenie, logarifm, f;

        s = s_mm[i] / 10.0;

        otnoshenie = (s + b) / s;

        logarifm = log(otnoshenie);

        f = koeff * logarifm;

        cout << fixed << s_mm[i] << "   " << f << endl;
    }
}
