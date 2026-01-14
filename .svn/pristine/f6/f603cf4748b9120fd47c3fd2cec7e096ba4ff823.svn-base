program IPEXP2100;

uses
  Forms,
  BASE in '..\..\DRLIB\COMMON\BASE.PAS' {FrmBase},
  DATAMODULE in '..\..\DRLIB\DATAMODULE\DATAMODULE.PAS' {DoctorDM: TDataModule},
  IPEXP2101 in 'IPEXP2101.pas' {Form1},
  ATTRALIB in '..\..\DRLIB\DATAMODULE\ATTRALIB.PAS';

{$R *.res}

begin
  Application.Initialize;
  Application.MainFormOnTaskbar := True;

  // 1) Create DataModule first
  Application.CreateForm(TDoctorDM, DoctorDM);
  // 2) Check DB connected (ถ้า DoctorDM มี property Database เหมือนตัวอย่างเดิม)
  if Assigned(DoctorDM) and Assigned(DoctorDM.Database) then
    if not DoctorDM.Database.Connected then
    begin
      Application.Terminate;
      Exit;
    end;

  // 3) Then create main form
  Application.CreateForm(TForm1, Form1);

  Application.Run;
end.

