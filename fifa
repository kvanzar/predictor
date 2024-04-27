#include <stdio.h>

void matrix_multiply(float A[][3], float B[][1], float result[][1], int m, int n, int p) {
    for (int i = 0; i < m; i++) {
        for (int j = 0; j < p; j++) {
            result[i][j] = 0;
            for (int k = 0; k < n; k++) {
                result[i][j] += A[i][k] * B[k][j];
            }
        }
    }
}

int main() {
    float X[5][3] = {{1, 1, 1}, {2, 3, 1}, {3, 5, 1}, {4, 2, 1}, {5, 4, 1}};
    float y[5][1] = {{2}, {3}, {4}, {2}, {4}};
    float theta[3][1] = {{0}, {0}, {0}};
    float alpha = 0.01;
    int num_iterations = 1000;
    for (int iter = 0; iter < num_iterations; iter++) {
        float predictions[5][1];
        float errors[5][1];
        float gradient[3][1] = {{0}, {0}, {0}};
        matrix_multiply(X, theta, predictions, 5, 3, 1);
        for (int i = 0; i < 5; i++) {
            errors[i][0] = predictions[i][0] - y[i][0];
        for (int i = 0; i < 5; i++) {
            for (int j = 0; j < 3; j++) {
                gradient[j][0] += (errors[i][0] * X[i][j]);
            }
        }
        for (int j = 0; j < 3; j++) {
            theta[j][0] -= (alpha / 5) * gradient[j][0];
        }
    }
    float new_input[3] = {6, 3, 1};
    float prediction[1];
    matrix_multiply(&new_input, theta, &prediction, 1, 3, 1);
    printf("Predicted wins: %f\n", prediction[0]);
    return 0;
}
