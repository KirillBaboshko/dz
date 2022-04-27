#include<iostream>
using namespace std;
class Poddergka
{
public:
	bool t = 1;
	virtual bool Get() = 0;
	virtual void Print() = 0;
	virtual void Problema() = 0;
};
class Otvetchik: public Poddergka
{
	int y;
public:
	Otvetchik()
	{
		int u;
		cout << "Если у вас проблемы с роутером нажмите-1,если вас интересует ваш договор нажмите-2,если вам нужен пароль от роутера нажмите-3,если у вас другие проблемы нажмите-0" << endl;
		cin >> u;
		y = u;
	}
	virtual void Print()
	{
		switch (y)
		{
		case 1:
		{
			cout << "Попробуйте перегрузить его,если не поможет позвоните ещё раз" << endl;
			t = 0;
			break;
		}
		case 2:
		{
			cout << "Номер вашего договора:23121. Задолжностей нет." << endl;
			t = 0;
			break;
		}
		case 3:
		{
			cout << "Номер вашего договора:23121. Пароль от роутера:47839." << endl;
			t = 0;
			break;
		}
		default:
		{
			cout << "Мы свяжем вас с оператором подождите минуту " << endl;
			break;
		}
		}
	}
	virtual bool Get()
	{
		return t;
	}
	virtual void Problema()
	{
		if (t==false)
		{
			cout << "Проблема решина!!"<<endl;
		}
	}
};

class Operator : public Poddergka
{
	int i;
public:
	Operator()
	{
		if (t)
		{
			int n;
			cout << "Здравствуйте чем могу помочь?(1-проблема с роутером,2-желаете заключить договор,0-связать с специалистом)" << endl;
			cin >> n;
			i = n;
		}
		
	}
	virtual void Print()
	{
		if (t)
		{
			switch (i)
			{
			case 1:
			{
				cout << "Подключите другие устройства. Чтобы убедиться в неисправности роутера, попробуйте подключить к нему другое оборудование — планшет, смартфон, ноутбук и т. д.\
					Осмотрите провода на факт целостности и качество контактов в разъемах.Нередко причиной того, что не работает маршрутизатор, является банальное передавливание кабеля или его повреждение домашними животными.Не менее редкая причина — отсутствие контактного соединения в одном из разъемов.\
					Подключите Интернет напрямую.На вопрос, что делать, если не работает роутер, специалисты поддержки рекомендуют подключиться к ноутбуку или ПК по сетевому кабелю.Это актуально, если ранее соединение происходило по Вай - Фай.Этот шаг позволяет определить, в чем именно проблема — в маршрутизаторе или настройках беспроводной сети." << endl;
				t = 0;
				break;
			}
			case 2:
			{
				cout << "Договор сроком на 2 года заключен с ежемесячной выплатой в 700р." << endl;
				t = 0;
				break;
			}
			default:
			{
				cout << "Мы свяжем вас с специалмстом подождите минуту " << endl;
				break;
			}
			}
		}
	}
	virtual bool Get()
	{
		return t;
	}
	virtual void Problema()
	{
		if (t == false)
		{
			cout << "Проблема решина!!" << endl;
		}
	}
};

class Spec : public Poddergka
{
	int j;
public:
	Spec()
	{
		if (t)
		{
			int о;
			cout << "Здравствуйте, решаем проблему на месте или дистанционно?(1-на месте,2-дистанционно)" << endl;
			cin >> о;
			j = о;
		}

	}
	virtual void Print()
	{
		if (t)
		{
			switch (j)
			{
			case 1:
			{
				cout << "Я выехал!!" << endl;
				t = 0;
				break;
			}
			default:
			{
				t = 0;
				break;
			}
			}
		}
	}
	virtual bool Get()
	{
		return t;
	}
	virtual void Problema()
	{
		if (t == false)
		{
			cout << "Проблема решина!!" << endl;
		}
	}
};
class Zvonok
{
public:
	Zvonok()
	{
		Otvetchik o;
		o.Print();
		o.Problema();
		if (o.Get())
		{
			Operator o1;
			o1.Print();
			o1.Problema();
			if (o1.Get())
			{
				Spec s;
				s.Print();
				s.Problema();
			}
		}
		
	}
};
void main()
{
	setlocale(0, "rus");
	Zvonok z;

 }
