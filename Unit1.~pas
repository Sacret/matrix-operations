unit Unit1;

interface

uses
  Windows, Messages, SysUtils, Variants, Classes, Graphics, Controls, Forms,
  Dialogs, StdCtrls, Grids, Spin, ExtCtrls, Buttons, jpeg;

type
  IntType = Integer;
  RealType= Real;
  ArrayType= Array[1..10,1..10] of RealType;

  TForm1 = class(TForm)
    Label2: TLabel;
    Label3: TLabel;
    StringGrid1: TStringGrid;
    Button2: TButton;
    SpinEdit1: TSpinEdit;
    SpinEdit2: TSpinEdit;
    Button3: TButton;
    StringGrid2: TStringGrid;
    StringGrid3: TStringGrid;
    Label5: TLabel;
    Label7: TLabel;
    SpinEdit3: TSpinEdit;
    SpinEdit4: TSpinEdit;
    Label8: TLabel;
    Label9: TLabel;
    Label10: TLabel;
    SpinEdit5: TSpinEdit;
    SpinEdit6: TSpinEdit;
    RadioGroup1: TRadioGroup;
    BitBtn1: TBitBtn;
    Image1: TImage;
    Image2: TImage;
    Image3: TImage;
    Image4: TImage;
    Label1: TLabel;
    Image5: TImage;
    Label4: TLabel;
    procedure Button2Click(Sender: TObject);
    procedure FormActivate(Sender: TObject);
    procedure StringGrid1KeyPress(Sender: TObject; var Key: Char);
    procedure Button3Click(Sender: TObject);
    procedure FormCreate(Sender: TObject);
    procedure BitBtn1Click(Sender: TObject);
  private
    { Private declarations }
  public
    { Public declarations }
  end;

var
  Form1: TForm1;
  NA,MA,NB,MB,NC,MC    : IntType;
  A, B, C              : ArrayType;



implementation

{$R *.dfm}

procedure TForm1.Button2Click(Sender: TObject);
begin
Close;
end;

procedure TForm1.FormActivate(Sender: TObject);
Var
  i,j : IntType;
begin
NA:= SpinEdit1.Value;
MA:= SpinEdit2.Value;

StringGrid1.RowCount:=NA+1;
StringGrid1.ColCount:=MA+1;
StringGrid1.ColWidths[0]:=60;
StringGrid1.Visible:=True;
Form1.StringGrid1.Cells[0,0]:='№';
Form1.StringGrid1.Cells[0,5]:='строка 5';
Form1.StringGrid1.Cells[0,6]:='строка 6';
Form1.StringGrid1.Cells[0,7]:='строка 7';
Form1.StringGrid1.Cells[0,8]:='строка 8';
Form1.StringGrid1.Cells[5,0]:='столбец 5';
Form1.StringGrid1.Cells[6,0]:='столбец 6';
Form1.StringGrid1.Cells[7,0]:='столбец 7';
Form1.StringGrid1.Cells[8,0]:='столбец 8';
For i:=1 to NA do
  For j:=1 to MA do
  begin
    Form1.StringGrid1.Cells[0,i]:='строка '+inttostr(i);
    Form1.StringGrid1.Cells[j,0]:='столбец '+inttostr(j);
  end;

NB:= SpinEdit3.Value;
MB:= SpinEdit4.Value;
StringGrid2.RowCount:=NB+1;
StringGrid2.ColCount:=MB+1;
StringGrid2.ColWidths[0]:=60;
StringGrid2.Visible:=True;
Form1.StringGrid2.Cells[0,0]:='№';
Form1.StringGrid2.Cells[0,5]:='строка 5';
Form1.StringGrid2.Cells[0,6]:='строка 6';
Form1.StringGrid2.Cells[0,7]:='строка 7';
Form1.StringGrid2.Cells[0,8]:='строка 8';
Form1.StringGrid2.Cells[5,0]:='столбец 5';
Form1.StringGrid2.Cells[6,0]:='столбец 6';
Form1.StringGrid2.Cells[7,0]:='столбец 7';
Form1.StringGrid2.Cells[8,0]:='столбец 8';
For i:=1 to NB do
  For j:=1 to MB do
  begin
    Form1.StringGrid2.Cells[0,i]:='строка '+inttostr(i);
    Form1.StringGrid2.Cells[j,0]:='столбец '+inttostr(j);
  end;
end;

procedure TForm1.Button3Click(Sender: TObject);
Var
   i,j : IntType;
begin
NA:= SpinEdit1.Value;
MA:= SpinEdit2.Value;
StringGrid1.RowCount:=NA+1;
StringGrid1.ColCount:=MA+1;
Randomize; {Подключаем генератор случайных чисел}
For i:=1 to NA do
  For j:= 1 to MA do
    StringGrid1.Cells[i,j]:= FloatToStr(Random(20)*0.1);

NB:= SpinEdit3.Value;
MB:= SpinEdit4.Value;
StringGrid2.RowCount:=NB+1;
StringGrid2.ColCount:=MB+1;
For i:=1 to NB do
  For j:= 1 to MB do
    StringGrid2.Cells[i,j]:= FloatToStr(Random(15)*0.1);
end;

procedure TForm1.FormCreate(Sender: TObject);
{Процедура открытия формы}
begin
  Button3.Click; {Вызов Button3 и автоматический ввод данных}
end;

procedure TForm1.StringGrid1KeyPress(Sender: TObject; var Key: Char);
{Процедура, позволяющая заменить '.' на ',' в текстовом режиме}
{Не забыть обработать событие OnKeyPress : StringGrid1KeyPress}
begin
  if Key = ',' then
    Key := DecimalSeparator; // запятую заменяем на разделитель для числа

  if Key = '.' then
    Key := DecimalSeparator; // точку заменяем на сепаратор (на всякий случай)

end;

procedure TForm1.BitBtn1Click(Sender: TObject);
Var
  i,j,k : IntType;
  S     : RealType;
begin
For i:=1 to NA do
        begin
        For j:=1 to MA do
            A[i,j]:=StrToFloat(StringGrid1.Cells[j,i]);
        end;
For i:=1 to NB do
        begin
        For j:=1 to MB do
            B[i,j]:=StrToFloat(StringGrid2.Cells[j,i]);
        end;
NC:= SpinEdit5.Value;
MC:= SpinEdit6.Value;
StringGrid3.RowCount:=NC+1;
StringGrid3.ColCount:=MC+1;
StringGrid3.ColWidths[0]:=60;
StringGrid3.Visible:=True;
Form1.StringGrid3.Cells[0,0]:='№';
For i:=1 to NC do
  For j:=1 to MC do
  begin
    Form1.StringGrid3.Cells[0,i]:='строка '+inttostr(i);
    Form1.StringGrid3.Cells[j,0]:='столбец '+inttostr(j);
  end;
Case RadioGroup1.ItemIndex of
  0: begin
     For i:=1 to NC do
        begin
        For j:=1 to MC do
            C[i,j]:= A[i,j]+B[i,j];
        end;
     end;
  1: begin
     For i:=1 to NA do
       For k:=1 to NB do
          begin
          S:=0;
          For j:=1 to NB do
            S:= S+A[i,j]*B[j,k];
          C[i,k]:=S;
          end;
     end;
  end;

For i:=1 to NC do
        begin
        For j:=1 to MC do
            StringGrid3.Cells[j,i]:=FloatToStr(C[i,j]);
        end;

end;

end.
