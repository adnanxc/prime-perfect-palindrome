# prime-perfect-palindrome
Write a function that checks if a number is in prime or not. If the number is prime, the function returns true, otherwise false. Also try functions for checking perfect numbers and palindromes.


#include <iostream>
using namespace std;

bool palindrome(int x){
    int n , rev = 0 , rem;
    n = x;

    while(n != 0){
        rem = n % 10;
        rev = (rev * 10) + rem;
        n = n / 10;
    }

    if (rev==x){
        return true;
    }

    else {
        return false;
    }
}

bool perfnum(int x){
    int sum = 0;
    for (int i=1; i<x; i++){

        if(x % i == 0){
            sum += i;
        }
    }

    if(sum==x){
        return true;
    }
    else {
        return false;
    }
}


bool prime(int a){
    int isPrime = 1;
    if(a<=1){
        return false;
    }
    else{
        for(int i=2; i<a; i++){
            if(a%i==0){
                isPrime = 0;
                break;
            }
        }

    }

    if(isPrime==1){
        return true;
    }
    else {
        return false;
    }

}

int main(){
    int x;
    cout << "Enter an integer: ";
    cin >> x;
    int isPrime = prime(x);
    if(isPrime==0){
        cout << x << " is not prime" << endl;
    }
    else{
        cout << x << " is prime" << endl;
    }


    int isPerf = perfnum(x);
    if(isPerf==0){
        cout << x << " is not a perfect number" << endl;
    }
    else{
        cout << x << " is a perfect number" << endl;
    }


    int isPal = palindrome(x);
    if(isPal==0){
        cout << x << " is not a palindrome" << endl;
    }
    else{
        cout << x << " is a palindrome" << endl;
    }



    return 0;
}
