# 4_practice_c-
Транспонування матриць
#include <iostream>
using namespace std;

// Transpose matrix
void transpose(const int src[][10], int dst[][10], int rows, int cols)
{
    for (int i = 0; i < rows; i++)
    {
        for (int j = 0; j < cols; j++)
        {
            dst[j][i] = src[i][j];
        }
    }
}

// Print matrix
void printMatrix(const int m[][10], int rows, int cols)
{
    for (int i = 0; i < rows; i++)
    {
        for (int j = 0; j < cols; j++)
        {
            cout << m[i][j] << " ";
        }
        cout << endl;
    }
}

int main()
{
    int rows, cols;
    int m[10][10];
    int t[10][10];

    // Input dimensions
    cin >> rows >> cols;

    // Input matrix
    for (int i = 0; i < rows; i++)
    {
        for (int j = 0; j < cols; j++)
        {
            cin >> m[i][j];
        }
    }

    // 1. Sum of rows
    cout << "ryadky ";

    for (int i = 0; i < rows; i++)
    {
        int sum = 0;

        for (int j = 0; j < cols; j++)
        {
            sum += m[i][j];
        }

        cout << sum << " ";
    }

    cout << endl;

    // 2. Sum of columns
    cout << "stovptsi ";

    for (int j = 0; j < cols; j++)
    {
        int sum = 0;

        for (int i = 0; i < rows; i++)
        {
            sum += m[i][j];
        }

        cout << sum << " ";
    }

    cout << endl;

    // 3. Transpose matrix
    transpose(m, t, rows, cols);

    cout << "transponovana" << endl;

    printMatrix(t, cols, rows);

    return 0;
}
