# Ćwiczenia 14 -- Android studio -- SimpleAdapter, ListView

💡 Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.

1. Utwórz projekt o nazwie SimpleAdapter na podstawie Empty Activity,
    dobierz odpowiednie API.
1. Otworzyć dokumentację:

   <[https://developer.android.com/reference/android/widget/SimpleAdapter](https://developer.android.com/reference/android/widget/SimpleAdapter)
   <https://developer.android.com/reference/android/widget/ListView#summary>
   <https://developer.android.com/reference/android/widget/AdapterView.OnItemClickListener>
   <https://developer.android.com/guide/topics/resources/string-resource>
   <https://developer.android.com/guide/topics/ui/dialogs>

1. Efekt końcowy:

   ![image1.png](media/image1.png)

1. Dodaj zależności.
1. Docelowo chcemy uzyskać coś na kształt, wybierz tematykę:
1. Dodaj w activity_main.xml listę

   ![image2](media/image2.png)

1. Dodaj pliki zdjęć do res ... .

  ![image3](media/image3.png)

  ![image4](media/image4.png)

1. Nazwy umieść w string-array:

1. Uzupełnij MainActivity.java:

  ![image5](media/image5.png)

1. Uzupełnij :

   ![image6](media/image6.png)

1. Dodaj elementy do hashMap (metoda put), następnie do listy (metoda
    add), kod w pętli for możesz zamknąć w metodę, która przyda się przy
    dodawaniu nowych produktów

  ![image7](media/image7.png)

1. Utwórz plik list_view_items.xml:

  ![image8](media/image8.png)

1. Dodaj do onCreate() elementy \[ from \] i \[ to \]

1. Na przykład:

  ![image9](media/image9.png)

1. Stwórz obiekt SimpleAdapter:

  ![image10](media/image10.png)

1. Ustaw adapter zgodnie z dokumentacją:

  ![image11](media/image11.png)

1. Na przykład:

  ![image12](media/image12.png)

1. Wykonaj zadania:

   a)  dodaj obsługę kliknięcia w item listView, wyświetl toast

   ![image13](media/image13.png)

   b)  dodaj obsługę kliknięcia w item ListView, nowa aktywność z opisem
        pozycji i obrazkiem, zapewnić powrót

   Zmień deklarację na

   ![image14](media/image14.png)

   ![image15](media/image15.png)

   ![image16](media/image16.png)

   ![image17](media/image17.png)

c)  dodaj opcję dodania nowej pozycji listy poprzez przycisk w kształcie
    (+)
![](media/image18.png)
[https://developer.android.com/guide/topics/ui/dialogs](https://developer.android.com/guide/topics/ui/dialogs)
![](media/image19.png)
![](media/image20.png)
Kształt dla przycisku:
![](media/image21.png)
oraz
![](media/image22.png)
d)  dodaj spiner dla wyboru nazwy obrazka:
> ![](media/image23.png)
>
> ![](media/image24.png)
>
> ![](media/image25.png)
e)  dodaj przycisk usuwający zaznaczony element listy.
> ![](media/image26.png)
>
> Oraz dodaj metodę na kształt:
>
> ![](media/image27.png)
f)  zadbaj o to, aby nowo dodany element był na liście po obrocie
    urządzenia o 90 stopni (ShredPreferences)
> <https://developer.android.com/training/data-storage/shared-preferences>
>
> <https://developer.android.com/reference/android/content/SharedPreferences>
>
> <https://developer.android.com/develop/ui/views/components/settings/use-saved-values>

1. KONIEC.
