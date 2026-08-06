#include <stdio.h>
int main()
{
    int sales[4][7];
    int i, j;

    printf("Enter sales of 4 products for 7 days:\n");

    for(i = 0; i < 4; i++)
    {
        printf("\nProduct %d:\n", i + 1);
        for(j = 0; j < 7; j++)
        {
            printf("Day %d: ", j + 1);
            scanf("%d", &sales[i][j]);
        }
    }

    int productTotal[4];
    printf("\nTotal Sales of Each Product:\n");

    for(i = 0; i < 4; i++)
    {
        productTotal[i] = 0;
        for(j = 0; j < 7; j++)
        {
            productTotal[i] += sales[i][j];
        }
        printf("Product %d = %d\n", i + 1, productTotal[i]);
    }

    int maxDay = 0, maxDaySales = 0;

    for(j = 0; j < 7; j++)
    {
        int dayTotal = 0;

        for(i = 0; i < 4; i++)
        {
            dayTotal += sales[i][j];
        }

        if(dayTotal > maxDaySales)
        {
            maxDaySales = dayTotal;
            maxDay = j;
        }
    }

    printf("\nDay with Highest Total Sales: Day %d\n", maxDay + 1);
    printf("Total Sales on that Day = %d\n", maxDaySales);

    int maxProduct = 0;

    for(i = 1; i < 4; i++)
    {
        if(productTotal[i] > productTotal[maxProduct])
        {
            maxProduct = i;
        }
    }

    printf("\nProduct with Highest Weekly Sales: Product %d\n", maxProduct + 1);
    printf("Weekly Sales = %d\n", productTotal[maxProduct]);
    return 0;
}
