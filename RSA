#include <iostream>
#include <cmath>
using namespace std;

int S1mple(int h)
{
	int c = 0, m;

	if ((h % 2) != 0)
	{
		m = 2;
		c = 1;
	}

	for (int i = 3; i < h; i++)
	{
		if (c == 1)
		{
			break;
		}

		for (int j = 1; j <= i - 1; j++)
		{
			if (((i % j) != 0) && ((h % i) != 0))
			{
				c = 1;
				m = i;
				break;
			}
		}
	}

	return m;
}

int privatekey(int h, int j)
{
	int o = 1, x = 1, m;

	while (o == 1)
	{
		if ((((x * j) % h) == 1) && (x != j))
		{
			m = x;
			o = -1;
		}

		x++;
	}

	return m;
}

int main()
{
	int p, q, e, f, d, P, n;
	unsigned long long int E;
	setlocale(LC_ALL, "rus");

	cout << "Введите p: ";
	cin >> p;
	cout << "Введите q: ";
	cin >> q;

	n = p * q;

	cout << "Введите сообщение (меньше " << n << "): ";
	cin >> P;

	f = (p - 1) * (q - 1);

	e = S1mple(f);

	cout << "Открытый ключ {" << e << ", " << n << "}" << endl;

	d = privatekey(f, e);

	cout << "Закрытый ключ {" << d << ", " << n << "}" << endl;

	E = pow(P, e);
	E = E % n;

	cout << "Зашифрованное сообщение: " << E << endl;

	E = pow(E, d);
	E = E % n;

	cout << "Расшифрованное сообщение: " << E << endl;

	system ("pause");
	return 0;
}
