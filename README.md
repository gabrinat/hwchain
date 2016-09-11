# hwchain
//В файле в стобик записаны целые числа. Напишите программу, которая определяет длину самой длинной цепочки идущих подряд одинаковых чисел и выводит результат в другой файл
var
    fin, fout: text;
    x, i, k, max: longint;
    a: array[1..1000] of longint;

begin
    k := 1;
    max := 1;
    assign(fin, 'input.txt');
    assign(fout, 'output.txt');
    reset(fin);
    rewrite(fout);
    while not eof(fin) do
    begin
        readln(fin, x);
        a[k] := x;
        k += 1;
    end;
    x := 1;
    for i := 1 to k - 1 do 
    begin
        if (a[i] + 1 = a[i + 1]) then
        begin
            x += 1;
            max := x;
        end
        else
            x := 0;
    end;
    writeln(fout, max);
    close(fin);
    close(fout);
end.
