# getline
입력 스트림에서 문자들을 읽은 후 인자로 받은 문자열에 저장
```c++
istream& getline (istream& is, string& str, char delim);
istream& getline (istream& is, string& str);
```
### cin.ignore()가 필요한 경우
- cin 사용 이후 getline을 사용하는 경우
- cin은 개행 문자를 입력 버퍼에 남겨두고 getline은 개행 문자를 포함하여 입력받으므로 getline 사용 전 cin.ignore()로 버퍼를 비워야 함
```c++
cin >> a;
cin.ignore();
getline(cin, b);
```
### cin.ignore()가 필요하지 않은 경우
- getline만 사용하는 경우
- getline은 개행 문자를 포함하여 입력받으므로 입력 버퍼에 개행 문자가 남지 않음
- 개행 문자가 존재하지 않는 버퍼를 cin.ignore()로 강제로 비울 경우 첫번째 문자 누락
```c++
getline(cin, a);
getline(cin, b);
```