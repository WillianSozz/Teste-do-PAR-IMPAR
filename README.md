unit Unit1;

{$mode objfpc}{$H+}

interface

uses
  Classes, SysUtils, Forms, Controls, Graphics, Dialogs, StdCtrls;

type

  { TForm1 }

  TForm1 = class(TForm)
    botao: TButton;
    campoNumero: TEdit;
    titulo: TLabel;
    txtnumero: TLabel;
    instrucao: TLabel;
    procedure botaoClick(Sender: TObject);
  private

  public

  end;

var
  Form1: TForm1;
  num: integer;

implementation

{$R *.lfm}

{ TForm1 }


procedure TForm1.botaoClick(Sender: TObject);
begin
     try
       num := strtoint(campoNumero.Text);
       if num mod 2 = 0 then
         begin
           instrucao.caption := 'Este numero é par!';
         end
       else
         begin
           instrucao.caption := 'Este numero é impar!';
         end;
        instrucao.alignment := taCenter;
     except
       on E: Exception do
              begin
                showmessage('Escreva um numero inteiro');
              end;
     end;
     campoNumero.text := '';
     campoNumero.Setfocus;

end;

end.
