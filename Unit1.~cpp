//---------------------------------------------------------------------------

#include <vcl.h>
#pragma hdrstop

#include "Unit1.h"
#include "mmsystem.h"
#include <IniFiles.hpp>
//---------------------------------------------------------------------------
#pragma package(smart_init)
#pragma resource "*.dfm"
TForm1 *Form1;
//---------------------------------------------------------------------------
void TForm1::setValues()
{
        charackterFallingSpeed = 20;
        platformsFallingSpeed = 4;
        platformsPoints = 0;
        fallingStart = false;
        timeThreshold = 30;
        jumpSpeed = 12;
        jumpHeight = 0;
        seconds = 0;
        counter = 0;
        score = 0;

        Ground -> Top = 1050;
        Platform1 -> Top = 880;
        Platform1 -> Left = 384;
        Platform2 -> Top = 700;
        Platform2 -> Left = 680;
        Platform3 -> Top = 520;
        Platform3 -> Left = 504;
        Platform4 -> Top = 340;
        Platform4 -> Left = 664;
        Platform5 -> Top = 160;
        Platform5 -> Left = 424;
        Platform6 -> Top = -20;
        Platform6 -> Left = 704;
        Character -> Top = 970;
        Character -> Left = 567;
}
//---------------------------------------------------------------------------
void TForm1::setHighscores()
{
        FirstPlace -> Caption = "1) " + nicknames[9] + "\t\t" + IntToStr(scoreboard[9]);
        SecondPlace -> Caption = "2) " + nicknames[8] + "\t\t" + IntToStr(scoreboard[8]);
        ThirdPlace -> Caption = "3) " + nicknames[7] + "\t\t" + IntToStr(scoreboard[7]);
        FourthPlace -> Caption = "4) " + nicknames[6] + "\t\t" + IntToStr(scoreboard[6]);
        FifthPlace -> Caption = "5) " + nicknames[5] + "\t\t" + IntToStr(scoreboard[5]);
        SixthPlace -> Caption = "6) " + nicknames[4] + "\t\t" + IntToStr(scoreboard[4]);
        SeventhPlace -> Caption = "7) " + nicknames[3] + "\t\t" + IntToStr(scoreboard[3]);
        EighthPlace -> Caption = "8) " + nicknames[2] + "\t\t" + IntToStr(scoreboard[2]);
        NinthPlace -> Caption = "9) " + nicknames[1] + "\t\t" + IntToStr(scoreboard[1]);
        TenthPlace -> Caption = "10) " + nicknames[0] + "\t\t" + IntToStr(scoreboard[0]);
}
//---------------------------------------------------------------------------
__fastcall TForm1::TForm1(TComponent* Owner)
        : TForm(Owner)
{
        setValues();

        TIniFile *ini = new TIniFile(ChangeFileExt(Application->ExeName, ".ini"));
        mvLeft = ini -> ReadInteger("Settings", "mvLeft", 65);
        mvRight = ini -> ReadInteger("Settings", "mvRight", 68);
        jump = ini -> ReadInteger("Settings", "jump", 74);

        scoreboard[0] = ini -> ReadInteger("Scoreboard", "scoreboard[0]", 100);
        scoreboard[1] = ini -> ReadInteger("Scoreboard", "scoreboard[1]", 200);
        scoreboard[2] = ini -> ReadInteger("Scoreboard", "scoreboard[2]", 300);
        scoreboard[3] = ini -> ReadInteger("Scoreboard", "scoreboard[3]", 400);
        scoreboard[4] = ini -> ReadInteger("Scoreboard", "scoreboard[4]", 500);
        scoreboard[5] = ini -> ReadInteger("Scoreboard", "scoreboard[5]", 600);
        scoreboard[6] = ini -> ReadInteger("Scoreboard", "scoreboard[6]", 700);
        scoreboard[7] = ini -> ReadInteger("Scoreboard", "scoreboard[7]", 800);
        scoreboard[8] = ini -> ReadInteger("Scoreboard", "scoreboard[8]", 900);
        scoreboard[9] = ini -> ReadInteger("Scoreboard", "scoreboard[9]", 1000);

        nicknames[0] = ini -> ReadString("Scoreboard", "nicknames[0]", "Anon 10");
        nicknames[1] = ini -> ReadString("Scoreboard", "nicknames[1]", "Anon 9");
        nicknames[2] = ini -> ReadString("Scoreboard", "nicknames[2]", "Anon 8");
        nicknames[3] = ini -> ReadString("Scoreboard", "nicknames[3]", "Anon 7");
        nicknames[4] = ini -> ReadString("Scoreboard", "nicknames[4]", "Anon 6");
        nicknames[5] = ini -> ReadString("Scoreboard", "nicknames[5]", "Anon 5");
        nicknames[6] = ini -> ReadString("Scoreboard", "nicknames[6]", "Anon 4");
        nicknames[7] = ini -> ReadString("Scoreboard", "nicknames[7]", "Anon 3");
        nicknames[8] = ini -> ReadString("Scoreboard", "nicknames[8]", "Anon 2");
        nicknames[9] = ini -> ReadString("Scoreboard", "nicknames[9]", "Anon 1");

        delete ini;

        setHighscores();
}
//---------------------------------------------------------------------------
                                //>>>>MAIN MENU<<<<//
//---------------------------------------------------------------------------
void TForm1::hideMenu()
{
        StartGame -> Enabled = false;
        StartGame -> Visible = false;
        Highscores -> Enabled = false;
        Highscores -> Visible = false;
        Options -> Enabled = false;
        Options -> Visible = false;
        Exit -> Enabled = false;
        Exit -> Visible = false;

        Return -> Enabled = true;
        Return -> Visible = true;
}
//---------------------------------------------------------------------------
void TForm1::showMenu()
{
        Return -> Enabled = false;
        Return -> Visible = false;
        Subtitle -> Caption = "";


        if (Form1 -> Tag == 1) // StartGame
        {
                NadakaN -> Visible = false;
                NadakaN -> Enabled = false;
                Trojan -> Visible = false;
                Trojan -> Enabled = false;
                Severian -> Visible = false;
                Severian -> Enabled = false;
                Kapi -> Visible = false;
                Kapi -> Enabled = false;
                Wloszek -> Visible = false;
                Wloszek -> Enabled = false;
                Bulgar -> Visible = false;
                Bulgar -> Enabled = false;
        }
        if (Form1 -> Tag == 2) // Highscores
        {
                FirstPlace -> Enabled = false;
                FirstPlace -> Visible= false;
                SecondPlace -> Enabled = false;
                SecondPlace -> Visible= false;
                ThirdPlace -> Enabled = false;
                ThirdPlace -> Visible= false;
                FourthPlace -> Enabled = false;
                FourthPlace -> Visible= false;
                FifthPlace -> Enabled = false;
                FifthPlace -> Visible= false;
                SixthPlace -> Enabled = false;
                SixthPlace -> Visible= false;
                SeventhPlace -> Enabled = false;
                SeventhPlace -> Visible= false;
                EighthPlace -> Enabled = false;
                EighthPlace -> Visible= false;
                NinthPlace -> Enabled = false;
                NinthPlace -> Visible= false;
                TenthPlace -> Enabled = false;
                TenthPlace -> Visible= false;
        }
        if (Form1 -> Tag ==3) // Options
        {
                Subtitle -> Font -> Size = 48;
                Option1Title -> Enabled = false;
                Option1Title -> Visible = false;
                Option1 -> Enabled = false;
                Option1 -> Visible = false;
                Option2Title -> Enabled = false;
                Option2Title -> Visible = false;
                Option2 -> Enabled = false;
                Option2 -> Visible = false;
                Option3Title -> Enabled = false;
                Option3Title -> Visible = false;
                Option3 -> Enabled = false;
                Option3 -> Visible = false;
                FactorySettings -> Enabled = false;
                FactorySettings -> Visible = false;
        }

        Form1 -> Tag = 0;

        StartGame -> Enabled = true;
        StartGame -> Visible = true;
        Highscores -> Enabled = true;
        Highscores -> Visible = true;
        Options -> Enabled = true;
        Options -> Visible = true;
        Exit -> Enabled = true;
        Exit -> Visible = true;
}
//---------------------------------------------------------------------------
void __fastcall TForm1::StartGameClick(TObject *Sender)
{
        Form1 -> Tag = 1;
        Subtitle -> Caption = "Wybierz postaæ:";
        hideMenu();
        Return -> Enabled = true;
        Return -> Visible = true;
        NadakaN -> Visible = true;
        NadakaN -> Enabled = true;
        Trojan -> Visible = true;
        Trojan -> Enabled = true;
        Severian -> Visible = true;
        Severian -> Enabled = true;
        Kapi -> Visible = true;
        Kapi -> Enabled = true;
        Wloszek -> Visible = true;
        Wloszek -> Enabled = true;
        Bulgar -> Visible = true;
        Bulgar -> Enabled = true;
}
//---------------------------------------------------------------------------
void __fastcall TForm1::StartGameMouseEnter(TObject *Sender)
{
        StartGame -> Caption = "< Rozpocznij grê >";
}
//---------------------------------------------------------------------------
void __fastcall TForm1::StartGameMouseLeave(TObject *Sender)
{
        StartGame -> Caption = "Rozpocznij grê";
}
//---------------------------------------------------------------------------
void __fastcall TForm1::HighscoresClick(TObject *Sender)
{
        Form1 -> Tag = 2;
        Subtitle -> Caption = "Najlepsze wyniki:";
        hideMenu();

        FirstPlace -> Enabled = true;
        FirstPlace -> Visible= true;
        SecondPlace -> Enabled = true;
        SecondPlace -> Visible= true;
        ThirdPlace -> Enabled = true;
        ThirdPlace -> Visible= true;
        FourthPlace -> Enabled = true;
        FourthPlace -> Visible= true;
        FifthPlace -> Enabled = true;
        FifthPlace -> Visible= true;
        SixthPlace -> Enabled = true;
        SixthPlace -> Visible= true;
        SeventhPlace -> Enabled = true;
        SeventhPlace -> Visible= true;
        EighthPlace -> Enabled = true;
        EighthPlace -> Visible= true;
        NinthPlace -> Enabled = true;
        NinthPlace -> Visible= true;
        TenthPlace -> Enabled = true;
        TenthPlace -> Visible= true;
}
//---------------------------------------------------------------------------
void __fastcall TForm1::HighscoresMouseEnter(TObject *Sender)
{
        Highscores -> Caption = "< Wyniki >";
}
//---------------------------------------------------------------------------
void __fastcall TForm1::HighscoresMouseLeave(TObject *Sender)
{
        Highscores -> Caption = "Wyniki";
}
//---------------------------------------------------------------------------
void __fastcall TForm1::OptionsClick(TObject *Sender)
{
        Form1 -> Tag = 3;
        Subtitle -> Font -> Size = 36;
        Subtitle -> Caption = "Ustawienia sterowania:";
        hideMenu();
        Option1Title -> Enabled = true;
        Option1Title -> Visible = true;
        Option1 -> Enabled = true;
        Option1 -> Visible = true;
        Option2Title -> Enabled = true;
        Option2Title -> Visible = true;
        Option2 -> Enabled = true;
        Option2 -> Visible = true;
        Option3Title -> Enabled = true;
        Option3Title -> Visible = true;
        Option3 -> Enabled = true;
        Option3 -> Visible = true;
        FactorySettings -> Enabled = true;
        FactorySettings -> Visible = true;

        setKeyCaption(Option1, &mvLeft);
        setKeyCaption(Option2, &mvRight);
        setKeyCaption(Option3, &jump);
        //Dodaj labele do ustawienia przyciskow i zrob eventy onclick do ich wyboru
}
//---------------------------------------------------------------------------
void __fastcall TForm1::OptionsMouseEnter(TObject *Sender)
{
        Options -> Caption = "< Opcje >";
}
//---------------------------------------------------------------------------
void __fastcall TForm1::OptionsMouseLeave(TObject *Sender)
{
        Options -> Caption = "Opcje";
}
//---------------------------------------------------------------------------
void __fastcall TForm1::ExitClick(TObject *Sender)
{
        Application -> Terminate();
}
//---------------------------------------------------------------------------
void __fastcall TForm1::ExitMouseEnter(TObject *Sender)
{
        Exit -> Caption = "< WyjdŸ z gry >";
}
//---------------------------------------------------------------------------
void __fastcall TForm1::ExitMouseLeave(TObject *Sender)
{
        Exit -> Caption = "WyjdŸ z gry";
}
//---------------------------------------------------------------------------
void __fastcall TForm1::ReturnClick(TObject *Sender)
{
        showMenu();
}
//---------------------------------------------------------------------------

void __fastcall TForm1::ReturnMouseEnter(TObject *Sender)
{
        Return -> Caption = "< Powrót >";
}
//---------------------------------------------------------------------------

void __fastcall TForm1::ReturnMouseLeave(TObject *Sender)
{
        Return -> Caption = "Powrót";
}
//---------------------------------------------------------------------------
                                //>>>>START GAME<<<<//
//---------------------------------------------------------------------------
void TForm1::gameplayON()
{
        Title -> Visible = false;
        Subtitle -> Caption = "";
        Return -> Enabled = false;
        Return -> Visible = false;
        NadakaN -> Visible = false;
        NadakaN -> Enabled = false;
        Trojan -> Visible = false;
        Trojan -> Enabled = false;
        Severian -> Visible = false;
        Severian -> Enabled = false;
        Kapi -> Visible = false;
        Kapi -> Enabled = false;
        Wloszek -> Visible = false;
        Wloszek -> Enabled = false;
        Bulgar -> Visible = false;
        Bulgar -> Enabled = false;

        Ground -> Enabled = true;
        Ground -> Visible = true;
        Platform1 -> Enabled = true;
        Platform1 -> Visible = true;
        Platform2 -> Enabled = true;
        Platform2 -> Visible = true;
        Platform3 -> Enabled = true;
        Platform3 -> Visible = true;
        Platform4 -> Enabled = true;
        Platform4 -> Visible = true;
        Platform5 -> Enabled = true;
        Platform5 -> Visible = true;
        Platform6 -> Enabled = true;
        Platform6 -> Visible = true;
        Character -> Enabled = true;
        Character -> Visible = true;
        ScoreTitle -> Enabled = true;
        ScoreTitle -> Visible = true;
        Score -> Enabled = true;
        Score -> Visible = true;
        TimeTitle -> Enabled = true;
        TimeTitle -> Visible = true;
        Time -> Enabled = true;
        Time -> Visible = true;
        SpeedBonus -> Enabled = true;
        SpeedBonus -> Visible = true;
        GameReset -> Visible = true;
        GameClose -> Enabled = true;
        GameClose -> Visible = true;

        Platform1 -> Tag = 0;
        Platform2 -> Tag = 0;
        Platform3 -> Tag = 0;
        Platform4 -> Tag = 0;
        Platform5 -> Tag = 0;
        Platform6 -> Tag = 0;

        GameControl -> Enabled = true;
        //Falling -> Enabled = true;
}
//---------------------------------------------------------------------------
void TForm1::gameplayOFF()
{
        Ground -> Enabled = false;
        Ground -> Visible = false;
        Platform1 -> Enabled = false;
        Platform1 -> Visible = false;
        Platform2 -> Enabled = false;
        Platform2 -> Visible = false;
        Platform3 -> Enabled = false;
        Platform3 -> Visible = false;
        Platform4 -> Enabled = false;
        Platform4 -> Visible = false;
        Platform5 -> Enabled = false;
        Platform5 -> Visible = false;
        Platform6 -> Enabled = false;
        Platform6 -> Visible = false;
        Character -> Enabled = false;
        Character -> Visible = false;
        ScoreTitle -> Enabled = false;
        ScoreTitle -> Visible = false;
        Score -> Enabled = false;
        Score -> Visible = false;
        TimeTitle -> Enabled = false;
        TimeTitle -> Visible = false;
        Time -> Enabled = false;
        Time -> Visible = false;
        SpeedBonus -> Enabled = false;
        SpeedBonus -> Visible = false;
        GameReset -> Visible = false;
        GameClose -> Enabled = false;
        GameClose -> Visible = false;

        GameControl -> Enabled = false;
        Falling -> Enabled = false;
}
//---------------------------------------------------------------------------
void __fastcall TForm1::WloszekClick(TObject *Sender)
{
        Character -> Picture -> LoadFromFile("img/Wloszek.bmp");
        setValues();
        gameplayON();
}
//---------------------------------------------------------------------------

void __fastcall TForm1::KapiClick(TObject *Sender)
{
        Character -> Picture -> LoadFromFile("img/Kapi.bmp");
        setValues();
        gameplayON();
}
//---------------------------------------------------------------------------

void __fastcall TForm1::SeverianClick(TObject *Sender)
{
        Character -> Picture -> LoadFromFile("img/Severian.bmp");
        setValues();
        gameplayON();
}
//---------------------------------------------------------------------------

void __fastcall TForm1::TrojanClick(TObject *Sender)
{
        Character -> Picture -> LoadFromFile("img/Trojan.bmp");
        setValues();
        gameplayON();
}
//---------------------------------------------------------------------------

void __fastcall TForm1::NadakaNClick(TObject *Sender)
{
        Character -> Picture -> LoadFromFile("img/NadakaN.bmp");
        setValues();
        gameplayON();
}
//---------------------------------------------------------------------------

void __fastcall TForm1::BulgarClick(TObject *Sender)
{
        Character -> Picture -> LoadFromFile("img/Bulgar.bmp");
        setValues();
        gameplayON();
}
//---------------------------------------------------------------------------
                                //>>>>GAMEPLAY ON<<<<//
//---------------------------------------------------------------------------
void __fastcall TForm1::MovingLeftTimer(TObject *Sender)
{
        if (Character -> Left > Background -> Left)
                Character -> Left -= 10;
}
//---------------------------------------------------------------------------
void __fastcall TForm1::MovingRightTimer(TObject *Sender)
{
        if (Character -> Left + Character -> Width < Background -> Left + Background -> Width)
                Character -> Left += 10;
}
//---------------------------------------------------------------------------
void __fastcall TForm1::JumpingTimer(TObject *Sender)
{
        jumpHeight--;
        if (jumpHeight > 0 && Character -> Top > Background -> Top)
        {
                Character -> Top -= jumpSpeed;
                if (Character -> Top <= Background -> Top)
                        jumpHeight = -1;

        }
        else if (jumpHeight <= 0)
        {
                Falling -> Enabled = true;
                if (jumpHeight <= -10) // gentle falling on the platform when platforms move  //pobaw ise z tym, bylo -20
                {
                        jumpHeight = 0;
                        Jumping -> Enabled = false;
                }
        }
}
//---------------------------------------------------------------------------
void __fastcall TForm1::FallingTimer(TObject *Sender)
{
        if (GameControl -> Enabled == true)
                Character -> Top += charackterFallingSpeed;
}
//---------------------------------------------------------------------------
void __fastcall TForm1::GameTimeTimer(TObject *Sender)
{
        seconds++;
        if (seconds == timeThreshold && counter <= 5)
        {
                if (counter < 5)
                {
                        charackterFallingSpeed++;
                        platformsFallingSpeed++;
                }
                else if (counter == 5)
                {
                        charackterFallingSpeed += 2;
                        platformsFallingSpeed += 2;
                }

                timeThreshold += 30;
                counter++;
        }
        Time -> Caption = seconds;
}
//---------------------------------------------------------------------------
void __fastcall TForm1::GameControlTimer(TObject *Sender)
{
        if (counter < 3)
        {
                if (counter == 0)
                        SpeedBonus -> Picture -> LoadFromFile("img/speed1.bmp");
                else if (counter == 1)
                        SpeedBonus -> Picture -> LoadFromFile("img/speed2.bmp");
                else if (counter == 2)
                        SpeedBonus -> Picture -> LoadFromFile("img/speed3.bmp");

                score = platformsPoints + seconds;
        }
        else if (counter > 2 && counter < 5)
        {
                if (counter == 3)
                        SpeedBonus -> Picture -> LoadFromFile("img/speed4.bmp");
                else if (counter == 4)
                        SpeedBonus -> Picture -> LoadFromFile("img/speed5.bmp");

                score = platformsPoints + seconds*2;
        }
        else if (counter == 5)
        {
                SpeedBonus -> Picture -> LoadFromFile("img/speed6.bmp");
                score = platformsPoints + seconds*3;
        }
        Score -> Caption = score;

        if (fallingStart == true) // new height of the platform
        {
                Platform1 -> Top += platformsFallingSpeed;
                if (Platform1 -> Top > 1100)
                {
                        Platform1 -> Tag = 0;
                        Platform1 -> Top = -20;
                        Platform1 -> Left = rand()%((Background -> Left + Background -> Width - Platform1 -> Width - 10) - (Background -> Left + 10) + 1) + Background -> Left + 10;
                }
                Platform2 -> Top += platformsFallingSpeed;
                if (Platform2 -> Top > 1100)
                {
                        Platform2 -> Tag = 0;
                        Platform2 -> Top = -20;
                        Platform2 -> Left = rand()%((Background -> Left + Background -> Width - Platform2 -> Width - 10) - (Background -> Left + 10) + 1) + Background -> Left + 10;
                }
                Platform3 -> Top += platformsFallingSpeed;
                if (Platform3 -> Top > 1100)
                {
                        Platform3 -> Tag = 0;
                        Platform3 -> Top = -20;
                        Platform3 -> Left = rand()%((Background -> Left + Background -> Width - Platform3 -> Width - 10) - (Background -> Left + 10) + 1) + Background -> Left + 10;
                }
                Platform4 -> Top += platformsFallingSpeed;
                if (Platform4 -> Top > 1100)
                {
                        Platform4 -> Tag = 0;
                        Platform4 -> Top = -20;
                        Platform4 -> Left = rand()%((Background -> Left + Background -> Width - Platform4 -> Width - 10) - (Background -> Left + 10) + 1) + Background -> Left + 10;
                }
                Platform5 -> Top += platformsFallingSpeed;
                if (Platform5 -> Top > 1100)
                {
                        Platform5 -> Tag = 0;
                        Platform5 -> Top = -20;
                        Platform5 -> Left = rand()%((Background -> Left + Background -> Width - Platform5 -> Width - 10) - (Background -> Left + 10) + 1) + Background -> Left + 10;
                }
                Platform6 -> Top += platformsFallingSpeed;
                if (Platform6 -> Top > 1100)
                {
                        Platform6 -> Tag = 0;
                        Platform6 -> Top = -20;
                        Platform6 -> Left = rand()%((Background -> Left + Background -> Width - Platform6 -> Width - 10) - (Background -> Left + 10) + 1) + Background -> Left + 10;
                }
                if (Ground -> Top < 2000)
                        Ground -> Top += platformsFallingSpeed;
        }
        else if (Character -> Top + Character -> Height >= Platform5 -> Top && Character -> Top + Character -> Height <= Platform5 -> Top + Platform5 -> Height
        && Character -> Left + Character -> Width >= Platform5 -> Left && Character -> Left <= Platform5 -> Left + Platform5 -> Width)
        {
                srand(time(NULL));

                GameTime -> Enabled = true;
                fallingStart = true;
        }

        if (Character -> Top + Character -> Height <= 1080 && Character -> Tag == 1 && Jumping -> Enabled == false && Platform1 -> Top <= 1100)
        {
                Character -> Top = Platform1 -> Top - Character -> Height;
                if (Platform1 -> Tag == 0)
                {
                        Platform1 -> Tag = 1;
                        platformsPoints += 10;
                }
        }
        else if (Character -> Top + Character -> Height <= 1080 && Character -> Tag == 2 && Jumping -> Enabled == false && Platform2 -> Top <= 1100)
        {
                Character -> Top = Platform2 -> Top - Character -> Height;
                if (Platform2 -> Tag == 0)
                {
                        Platform2 -> Tag = 1;
                        platformsPoints += 10;
                }
        }
        else if (Character -> Top + Character -> Height <= 1080 && Character -> Tag == 3 && Jumping -> Enabled == false && Platform3 -> Top <= 1100)
        {
                Character -> Top = Platform3 -> Top - Character -> Height;
                if (Platform3 -> Tag == 0)
                {
                        Platform3 -> Tag = 1;
                        platformsPoints += 10;
                }
        }
        else if (Character -> Top + Character -> Height <= 1080 && Character -> Tag == 4 && Jumping -> Enabled == false && Platform4 -> Top <= 1100)
        {
                Character -> Top = Platform4 -> Top - Character -> Height;
                if (Platform4 -> Tag == 0)
                {
                        Platform4 -> Tag = 1;
                        platformsPoints += 10;
                }
        }
        else if (Character -> Top + Character -> Height <= 1080 && Character -> Tag == 5 && Jumping -> Enabled == false && Platform5 -> Top <= 1100)
        {
                Character -> Top = Platform5 -> Top - Character -> Height;
                if (Platform5 -> Tag == 0)
                {
                        Platform5 -> Tag = 1;
                        platformsPoints += 10;
                }
        }
        else if (Character -> Top + Character -> Height <= 1080 && Character -> Tag == 6 && Jumping -> Enabled == false && Platform6 -> Top <= 1100)
        {
                Character -> Top = Platform6 -> Top - Character -> Height;
                if (Platform6 -> Tag == 0)
                {
                        Platform6 -> Tag = 1;
                        platformsPoints += 10;
                }
        }
        else if (Character -> Tag == 7 && Jumping -> Enabled == false && Ground -> Top < 1080)
                Character -> Top = Ground -> Top - Character -> Height;

        if (Character -> Top + Character -> Height >= Platform1 -> Top
        && Character -> Top + Character -> Height <= Platform1 -> Top + Platform1 -> Height)
        {
                if (Character -> Left + Character -> Width < Platform1 -> Left && jumpHeight <= 0 // jumpHeight to reduce floating in air
                || Character -> Left > Platform1 -> Left + Platform1 -> Width && jumpHeight <= 0) //and easier jump on platform
                {
                        Falling -> Enabled = true;
                        Character -> Tag = 0;
                }
                else // Character's tag because jump possible only on the platform
                {
                        Falling -> Enabled = false;
                        Character -> Tag = 1;
                }
        }
        else if (Character -> Top + Character -> Height >= Platform2 -> Top
        && Character -> Top + Character -> Height <= Platform2 -> Top + Platform2 -> Height)
        {
                if (Character -> Left + Character -> Width < Platform2 -> Left && jumpHeight <= 0 // jumpHeight to reduce floating in air
                || Character -> Left > Platform2 -> Left + Platform2 -> Width && jumpHeight <= 0) //and easier jump on platform
                {
                        Falling -> Enabled = true;
                        Character -> Tag = 0;
                }
                else // Character's tag because jump possible only on the platform
                {
                        Falling -> Enabled = false;
                        Character -> Tag = 2;
                }
        }
        else if (Character -> Top + Character -> Height >= Platform3 -> Top
        && Character -> Top + Character -> Height <= Platform3 -> Top + Platform3 -> Height)
        {
                if (Character -> Left + Character -> Width < Platform3 -> Left && jumpHeight <= 0 // jumpHeight to reduce floating in air
                || Character -> Left > Platform3 -> Left + Platform3 -> Width && jumpHeight <= 0) //and easier jump on platform
                {
                        Falling -> Enabled = true;
                        Character -> Tag = 0;
                }
                else // Character's tag because jump possible only on the platform
                {
                        Falling -> Enabled = false;
                        Character -> Tag = 3;
                }
        }
        else if (Character -> Top + Character -> Height >= Platform4 -> Top
        && Character -> Top + Character -> Height <= Platform4 -> Top + Platform4 -> Height)
        {
                if (Character -> Left + Character -> Width < Platform4 -> Left && jumpHeight <= 0 // jumpHeight to reduce floating in air
                || Character -> Left > Platform4 -> Left + Platform4 -> Width && jumpHeight <= 0) //and easier jump on platform
                {
                        Falling -> Enabled = true;
                        Character -> Tag = 0;
                }
                else // Character's tag because jump possible only on the platform
                {
                        Falling -> Enabled = false;
                        Character -> Tag = 4;
                }
        }
        else if (Character -> Top + Character -> Height >= Platform5 -> Top
        && Character -> Top + Character -> Height <= Platform5 -> Top + Platform5 -> Height)
        {
                if (Character -> Left + Character -> Width < Platform5 -> Left && jumpHeight <= 0 // jumpHeight to reduce floating in air
                || Character -> Left > Platform5 -> Left + Platform5 -> Width && jumpHeight <= 0) // and easier jump on platform
                {
                        Falling -> Enabled = true;
                        Character -> Tag = 0;
                }
                else // Character's tag because jump possible only on the platform
                {
                        Falling -> Enabled = false;
                        Character -> Tag = 5;
                }
        }
        else if (Character -> Top + Character -> Height >= Platform6 -> Top
        && Character -> Top + Character -> Height <= Platform6 -> Top + Platform6 -> Height)
        {
                if (Character -> Left + Character -> Width < Platform6 -> Left && jumpHeight <= 0 // jumpHeight to reduce floating in air
                || Character -> Left > Platform6 -> Left + Platform6 -> Width && jumpHeight <= 0) // and easier jump on platform
                {
                        Falling -> Enabled = true;
                        Character -> Tag = 0;
                }
                else // Character's tag because jump possible only on the platform
                {
                        Falling -> Enabled = false;
                        Character -> Tag = 6;
                }
        }
        else if (Character -> Top + Character -> Height >= Ground -> Top
        && Character -> Top + Character -> Height <= Ground -> Top + Ground -> Height)
        {
                if (Character -> Left + Character -> Width < Ground -> Left && jumpHeight <= 0 // jumpHeight to reduce floating in air
                || Character -> Left > Ground -> Left + Ground -> Width && jumpHeight <= 0) // and easier jump on platform
                {
                        Falling -> Enabled = true;
                        Character -> Tag = 0;
                }
                else // Character's tag because jump possible only on the platform
                {
                        Falling -> Enabled = false;
                        Character -> Tag = 7;
                }
        }
        else if (Jumping -> Enabled == false)
        {
                Falling -> Enabled = true;
                Character -> Tag = 0;
        }

        if (Character -> Top > 1100)
        {
                PlaySound("snd/lose.wav", NULL, SND_ASYNC);
                GameTime -> Enabled = false;
                MovingLeft -> Enabled = false;
                MovingRight -> Enabled = false;
                Jumping -> Enabled = false;
                Falling -> Enabled = false;
                GameControl -> Enabled = false;
                GameReset -> Enabled = true;
                Subtitle -> Caption = "Koniec Gry!";

                int i = 9;
                for (i = 9; i >= 0; i--)
                {
                        if (score > scoreboard[i])
                        {
                                place = i;
                                GameReset -> Enabled = false;
                                GameClose -> Enabled = false;
                                Information -> Enabled = true;
                                Information -> Visible = true;
                                UserNickname -> Enabled = true;
                                UserNickname -> Visible = true;
                                temp = "";
                                UserNickname -> Caption = temp;
                                i = -1;
                        }
                }
        }
}
//---------------------------------------------------------------------------
void __fastcall TForm1::FormKeyDown(TObject *Sender, WORD &Key,
      TShiftState Shift)
{
        if (GameControl -> Enabled == true)
        {
                if (Key == mvLeft)
                        MovingLeft -> Enabled = true;
                if (Key == mvRight)
                        MovingRight -> Enabled = true;
        }
        else if (Form1 -> Tag == 3 && Option1 -> Tag == 1)
        {
                mvLeft = Key;
                setKeyCaption(Option1, &mvLeft);

                TIniFile *ini = new TIniFile(ChangeFileExt(Application->ExeName, ".ini"));
                ini -> WriteInteger("Settings", "mvLeft", mvLeft);
                delete ini;

                Option1 -> Tag = 0;
        }
        else if (Form1 -> Tag == 3 && Option2 -> Tag == 1)
        {
                mvRight = Key;
                setKeyCaption(Option2, &mvRight);

                TIniFile *ini = new TIniFile(ChangeFileExt(Application->ExeName, ".ini"));
                ini -> WriteInteger("Settings", "mvRight", mvRight);
                delete ini;

                Option2 -> Tag = 0;
        }
        else if (Form1 -> Tag == 3 && Option3 -> Tag == 1)
        {
                jump = Key;
                setKeyCaption(Option3, &jump);

                TIniFile *ini = new TIniFile(ChangeFileExt(Application->ExeName, ".ini"));
                ini -> WriteInteger("Settings", "jump", jump);
                delete ini;

                Option3 -> Tag = 0;
        }
        else if (Information -> Enabled == true)
        {
                if (Key == 'A')
                        temp = temp + "A";
                if (Key == 'B')
                        temp = temp + "B";
                if (Key == 'C')
                        temp = temp + "C";
                if (Key == 'D')
                        temp = temp + "D";
                if (Key == 'E')
                        temp = temp + "E";
                if (Key == 'F')
                        temp = temp + "F";
                if (Key == 'G')
                        temp = temp + "G";
                if (Key == 'H')
                        temp = temp + "H";
                if (Key == 'I')
                        temp = temp + "I";
                if (Key == 'J')
                        temp = temp + "J";
                if (Key == 'K')
                        temp = temp + "K";
                if (Key == 'L')
                        temp = temp + "L";
                if (Key == 'M')
                        temp = temp + "M";
                if (Key == 'N')
                        temp = temp + "N";
                if (Key == 'O')
                        temp = temp + "O";
                if (Key == 'P')
                        temp = temp + "P";
                if (Key == 'Q')
                        temp = temp + "Q";
                if (Key == 'R')
                        temp = temp + "R";
                if (Key == 'S')
                        temp = temp + "S";
                if (Key == 'T')
                        temp = temp + "T";
                if (Key == 'U')
                        temp = temp + "U";
                if (Key == 'V')
                        temp = temp + "V";
                if (Key == 'W')
                        temp = temp + "W";
                if (Key == 'X')
                        temp = temp + "X";
                if (Key == 'Y')
                        temp = temp + "Y";
                if (Key == 'Z')
                        temp = temp + "Z";
                if (Key == '1')
                        temp = temp + "1";
                if (Key == '2')
                        temp = temp + "2";
                if (Key == '3')
                        temp = temp + "3";
                if (Key == '4')
                        temp = temp + "4";
                if (Key == '5')
                        temp = temp + "5";
                if (Key == '6')
                        temp = temp + "6";
                if (Key == '7')
                        temp = temp + "7";
                if (Key == '8')
                        temp = temp + "8";
                if (Key == '9')
                        temp = temp + "9";
                if (Key == '0')
                        temp = temp + "0";
                if (Key == VK_BACK && temp != "")
                        temp.Delete(temp.Length(), 1);
                if (Key == VK_RETURN && temp != "")
                {
                        scoreboard[place] = score;
                        nicknames[place] = temp;
                        Information -> Enabled = false;
                        Information -> Visible = false;
                        UserNickname -> Enabled = false;
                        UserNickname -> Visible = false;
                        Title -> Enabled = true;
                        Title -> Visible = true;
                        gameplayOFF();
                        HighscoresClick(Highscores);
                        setHighscores();

                        TIniFile *ini = new TIniFile(ChangeFileExt(Application->ExeName, ".ini"));

                        ini -> WriteInteger("Scoreboard", "scoreboard[0]", scoreboard[0]);
                        ini -> WriteInteger("Scoreboard", "scoreboard[1]", scoreboard[1]);
                        ini -> WriteInteger("Scoreboard", "scoreboard[2]", scoreboard[2]);
                        ini -> WriteInteger("Scoreboard", "scoreboard[3]", scoreboard[3]);
                        ini -> WriteInteger("Scoreboard", "scoreboard[4]", scoreboard[4]);
                        ini -> WriteInteger("Scoreboard", "scoreboard[5]", scoreboard[5]);
                        ini -> WriteInteger("Scoreboard", "scoreboard[6]", scoreboard[6]);
                        ini -> WriteInteger("Scoreboard", "scoreboard[7]", scoreboard[7]);
                        ini -> WriteInteger("Scoreboard", "scoreboard[8]", scoreboard[8]);
                        ini -> WriteInteger("Scoreboard", "scoreboard[9]", scoreboard[9]);

                        ini -> WriteString("Scoreboard", "nicknames[0]", nicknames[0]);
                        ini -> WriteString("Scoreboard", "nicknames[1]", nicknames[1]);
                        ini -> WriteString("Scoreboard", "nicknames[2]", nicknames[2]);
                        ini -> WriteString("Scoreboard", "nicknames[3]", nicknames[3]);
                        ini -> WriteString("Scoreboard", "nicknames[4]", nicknames[4]);
                        ini -> WriteString("Scoreboard", "nicknames[5]", nicknames[5]);
                        ini -> WriteString("Scoreboard", "nicknames[6]", nicknames[6]);
                        ini -> WriteString("Scoreboard", "nicknames[7]", nicknames[7]);
                        ini -> WriteString("Scoreboard", "nicknames[8]", nicknames[8]);
                        ini -> WriteString("Scoreboard", "nicknames[9]", nicknames[9]);

                        delete ini;
                }
                UserNickname -> Caption = temp;
        }
}
//---------------------------------------------------------------------------
void __fastcall TForm1::FormKeyUp(TObject *Sender, WORD &Key,
      TShiftState Shift)
{
        if (GameControl -> Enabled == true)
        {
                if (Key == mvLeft)
                MovingLeft -> Enabled = false;
                if (Key == mvRight)
                MovingRight -> Enabled = false;
                if (Key == jump && Jumping -> Enabled == false && Character -> Tag > 0)                { // Jumping disabled beceause of multiple jump
                        jumpHeight = 25;
                        Falling -> Enabled = false;
                        Jumping -> Enabled = true;
                        PlaySound("snd/jump.wav", NULL, SND_ASYNC);
                }
        }
}
//---------------------------------------------------------------------------
void __fastcall TForm1::GameResetClick(TObject *Sender)
{
        setValues();
        Time -> Caption = seconds;
        Subtitle -> Caption = "";
        GameControl -> Enabled = true;
        //Falling -> Enabled = true;
        GameReset -> Enabled = false;
}
//---------------------------------------------------------------------------
void __fastcall TForm1::GameResetMouseEnter(TObject *Sender)
{
        GameReset -> Caption = "< Zacznij od nowa >";
}
//---------------------------------------------------------------------------
void __fastcall TForm1::GameResetMouseLeave(TObject *Sender)
{
        GameReset -> Caption = "Zacznij od nowa";
}
//---------------------------------------------------------------------------
void __fastcall TForm1::GameCloseClick(TObject *Sender)
{
        gameplayOFF();
        Title -> Enabled = true;
        Title -> Visible = true;
        showMenu();
}
//---------------------------------------------------------------------------
void __fastcall TForm1::GameCloseMouseEnter(TObject *Sender)
{
        GameClose -> Caption = "< Powrót do menu >";
}
//---------------------------------------------------------------------------
void __fastcall TForm1::GameCloseMouseLeave(TObject *Sender)
{
        GameClose -> Caption = "Powrót do menu";
}
//---------------------------------------------------------------------------
                                //>>>>OPTIONS<<<<//
//---------------------------------------------------------------------------
void TForm1::setKeyCaption(TLabel *Option, WORD *UserKey)
{
        if (*UserKey == 1)
                Option -> Caption = "LPM";
        else if (*UserKey == 2)
                Option -> Caption = "PPM";
        else if (*UserKey == 4)
                Option -> Caption = "ŒPM";
        else if (*UserKey == 8)
                Option -> Caption = "BACKSPACE";
        else if (*UserKey == 9)
                Option -> Caption = "TAB";
        else if (*UserKey == 12)
                Option -> Caption = "CLEAR";
        else if (*UserKey == 13)
                Option -> Caption = "ENTER";
        else if (*UserKey == 16)
                Option -> Caption = "SHIFT";
        else if (*UserKey == 17)
                Option -> Caption = "CTRL (ALT GR)";
        else if (*UserKey == 18)
                Option -> Caption = "ALT";
        else if (*UserKey == 19)
                Option -> Caption = "PAUSE";
        else if (*UserKey == 20)
                Option -> Caption = "CAPS LOCK";
        else if (*UserKey == 27)
                Option -> Caption = "ESC";
        else if (*UserKey == 32)
                Option -> Caption = "SPACJA";
        else if (*UserKey == 33)
                Option -> Caption = "PAGE UP";
        else if (*UserKey == 34)
                Option -> Caption = "PAGE DOWN";
        else if (*UserKey == 35)
                Option -> Caption = "END";
        else if (*UserKey == 36)
                Option -> Caption = "HOME";
        else if (*UserKey == 37)
                Option -> Caption = "STRZA£KA W LEWO";
        else if (*UserKey == 38)
                Option -> Caption = "STRZA£KA W GÓRÊ";
        else if (*UserKey == 39)
                Option -> Caption = "STRZA£KA W PRAWO";
        else if (*UserKey == 40)
                Option -> Caption = "STRZA£KA W DÓ£";
        else if (*UserKey ==41)
                Option -> Caption = "SELECT";
        else if (*UserKey == 42)
                Option -> Caption = "PRINT";
        else if (*UserKey == 43)
                Option -> Caption = "EXECUTE";
        else if (*UserKey == 44)
                Option -> Caption = "PRINT SCREEN";
        else if (*UserKey == 45)
                Option -> Caption = "INS";
        else if (*UserKey == 46)
                Option -> Caption = "DEL";
        else if (*UserKey == 47)
                Option -> Caption = "HELP";
        else if (*UserKey >= 48 && *UserKey <= 57 || *UserKey >= 65 && *UserKey <= 90)
                Option -> Caption = char(*UserKey);
        else if (*UserKey == 91)
                Option -> Caption = "LEWY KLAWISZ WIN";
        else if (*UserKey == 92)
                Option -> Caption = "PRAWY KLAWISZ WIN";
        else if (*UserKey == 93)
                Option -> Caption = "KLAWISZ APLIKACJI";
        else if (*UserKey == 95)
                Option -> Caption = "SLEEP";
        else if (*UserKey == 96)
                Option -> Caption = "NUMPAD 0";
        else if (*UserKey == 97)
                Option -> Caption = "NUMPAD 1";
        else if (*UserKey == 98)
                Option -> Caption = "NUMPAD 2";
        else if (*UserKey == 99)
                Option -> Caption = "NUMPAD 3";
        else if (*UserKey == 100)
                Option -> Caption = "NUMPAD 4";
        else if (*UserKey == 101)
                Option -> Caption = "NUMPAD 5";
        else if (*UserKey == 102)
                Option -> Caption = "NUMPAD 6";
        else if (*UserKey == 103)
                Option -> Caption = "NUMPAD 7";
        else if (*UserKey == 104)
                Option -> Caption = "NUMPAD 8";
        else if (*UserKey == 105)
                Option -> Caption = "NUMPAD 9";
        else if (*UserKey == 106)
                Option -> Caption = "NUMPAD *";
        else if (*UserKey == 107)
                Option -> Caption = "NUMPAD +";
        else if (*UserKey == 108)
                Option -> Caption = "SEPARATOR";
        else if (*UserKey == 109)
                Option -> Caption = "NUMPAD -";
        else if (*UserKey == 110)
                Option -> Caption = "NUMPAD .";
        else if (*UserKey == 111)
                Option -> Caption = "NUMPAD /";
        else if (*UserKey == 112)
                Option -> Caption = "F1";
        else if (*UserKey == 113)
                Option -> Caption = "F2";
        else if (*UserKey == 114)
                Option -> Caption = "F3";
        else if (*UserKey == 115)
                Option -> Caption = "F4";
        else if (*UserKey == 116)
                Option -> Caption = "F5";
        else if (*UserKey == 117)
                Option -> Caption = "F6";
        else if (*UserKey == 118)
                Option -> Caption = "F7";
        else if (*UserKey == 119)
                Option -> Caption = "F8";
        else if (*UserKey == 120)
                Option -> Caption = "F9";
        else if (*UserKey == 121)
                Option -> Caption = "F10";
        else if (*UserKey == 122)
                Option -> Caption = "F11";
        else if (*UserKey == 123)
                Option -> Caption = "F12";
        else if (*UserKey == 124)
                Option -> Caption = "F13";
        else if (*UserKey == 125)
                Option -> Caption = "F14";
        else if (*UserKey == 126)
                Option -> Caption = "F15";
        else if (*UserKey == 127)
                Option -> Caption = "F16";
        else if (*UserKey == 128)
                Option -> Caption = "F17";
        else if (*UserKey == 129)
                Option -> Caption = "F18";
        else if (*UserKey == 130)
                Option -> Caption = "F19";
        else if (*UserKey == 131)
                Option -> Caption = "F20";
        else if (*UserKey == 132)
                Option -> Caption = "F21";
        else if (*UserKey == 133)
                Option -> Caption = "F22";
        else if (*UserKey == 134)
                Option -> Caption = "F23";
        else if (*UserKey == 135)
                Option -> Caption = "F24";
        else if (*UserKey == 144)
                Option -> Caption = "NUM LOCK";
        else if (*UserKey == 145)
                Option -> Caption = "SCROLL LOCK";
        else if (*UserKey == 160)
                Option -> Caption = "LEWY SHIFT";
        else if (*UserKey == 161)
                Option -> Caption = "PRAWY SHIFT";
        else if (*UserKey == 162)
                Option -> Caption = "LEWY CTRL";
        else if (*UserKey == 163)
                Option -> Caption = "PRAWY CTRL";
        else if (*UserKey == 164)
                Option -> Caption = "LEWY KL. MENU";
        else if (*UserKey == 165)
                Option -> Caption = "PRAWY KL. MENU";
        else if (*UserKey == 166)
                Option -> Caption = "BROWSER BACK";
        else if (*UserKey == 167)
                Option -> Caption = "BROWSER FORWARD";
        else if (*UserKey == 168)
                Option -> Caption = "BROWSER REFRESH";
        else if (*UserKey == 169)
                Option -> Caption = "BROWSER STOP";
        else if (*UserKey == 170)
                Option -> Caption = "BROWSER SEARCH";
        else if (*UserKey == 171)
                Option -> Caption = "BROWSER FAVORITES";
        else if (*UserKey == 172)
                Option -> Caption = "BROWSER START/HOME";
        else if (*UserKey == 173)
                Option -> Caption = "VOLUME MUTE";
        else if (*UserKey == 174)
                Option -> Caption = "BROWSER DOWN";
        else if (*UserKey == 175)
                Option -> Caption = "BROWSER UP";
        else if (*UserKey == 176)
                Option -> Caption = "NEXT TRACK";
        else if (*UserKey == 177)
                Option -> Caption = "PREVIOUS TRACK";
        else if (*UserKey == 178)
                Option -> Caption = "STOP MEDIA";
        else if (*UserKey == 179)
                Option -> Caption = "PLAY/PAUSE";
        else if (*UserKey == 180)
                Option -> Caption = "START MAIL";
        else if (*UserKey == 181)
                Option -> Caption = "SELECT MEDIA";
        else if (*UserKey == 182)
                Option -> Caption = "START APP 1";
        else if (*UserKey == 183)
                Option -> Caption = "START APP 2";
        else if (*UserKey == 186)
                Option -> Caption = ";";
        else if (*UserKey == 187)
                Option -> Caption = "+";
        else if (*UserKey == 188)
                Option -> Caption = ",";

        else if (*UserKey == 189)
                Option -> Caption = "-";
        else if (*UserKey == 190)
                Option -> Caption = ".";
        else if (*UserKey == 191)
                Option -> Caption = "/";
        else if (*UserKey == 192)
                Option -> Caption = "~";
        else if (*UserKey == 219)
                Option -> Caption = "[";
        else if (*UserKey == 220)
                Option -> Caption = "\\";
        else if (*UserKey == 221)
                Option -> Caption = "]";
        else if (*UserKey == 222)
                Option -> Caption = "\"";
        else if (*UserKey == 250)
                Option -> Caption = "PLAY";
        else if (*UserKey == 251)
                Option -> Caption = "ZOOM";
        else if (*UserKey == 253)
                Option -> Caption = "PA1";
        else if (*UserKey == 254)
                Option -> Caption = "CLEAR";
}
//---------------------------------------------------------------------------
void __fastcall TForm1::Option1Click(TObject *Sender)
{
        if (Option2 -> Tag == 0 && Option3 -> Tag == 0)
        {
                Option1 -> Caption = "Naciœnij przycisk...";
                Option1 -> Tag = 1;
        }
}
//---------------------------------------------------------------------------

void __fastcall TForm1::Option1MouseEnter(TObject *Sender)
{
        if (Option1 -> Tag == 0)
                Option1 -> Caption = "< " + Option1 -> Caption + " >";
}
//---------------------------------------------------------------------------

void __fastcall TForm1::Option1MouseLeave(TObject *Sender)
{
        if (Option1 -> Tag == 0)
                setKeyCaption(Option1, &mvLeft);
}
//---------------------------------------------------------------------------
void __fastcall TForm1::Option2Click(TObject *Sender)
{
        if (Option1 -> Tag == 0 && Option3 -> Tag == 0)
        {
                Option2 -> Caption = "Naciœnij przycisk...";
                Option2 -> Tag = 1;
        }
}
//---------------------------------------------------------------------------
void __fastcall TForm1::Option2MouseEnter(TObject *Sender)
{
        if (Option2 -> Tag == 0)
                Option2 -> Caption = "< " + Option2 -> Caption + " >";
}
//---------------------------------------------------------------------------

void __fastcall TForm1::Option2MouseLeave(TObject *Sender)
{
        if (Option2 -> Tag == 0)
                setKeyCaption(Option2, &mvRight);
}
//---------------------------------------------------------------------------

void __fastcall TForm1::Option3Click(TObject *Sender)
{
        if (Option1 -> Tag == 0 && Option2 -> Tag == 0)
        {
                Option3 -> Caption = "Naciœnij przycisk...";
                Option3 -> Tag = 1;
        }
}
//---------------------------------------------------------------------------
void __fastcall TForm1::Option3MouseEnter(TObject *Sender)
{
        if (Option3 -> Tag == 0)
                Option3 -> Caption = "< " + Option3 -> Caption + " >";
}
//---------------------------------------------------------------------------

void __fastcall TForm1::Option3MouseLeave(TObject *Sender)
{
        if (Option3 -> Tag == 0)
                setKeyCaption(Option3, &jump);
}
//---------------------------------------------------------------------------
void __fastcall TForm1::FactorySettingsClick(TObject *Sender)
{
        if (Option1 -> Tag == 0 && Option2 -> Tag == 0 && Option3 -> Tag == 0)
        {
                mvLeft = 65;
                setKeyCaption(Option1, &mvLeft);
                mvRight = 68;
                setKeyCaption(Option2, &mvRight);
                jump = 74;
                setKeyCaption(Option3, &jump);

                TIniFile *ini = new TIniFile(ChangeFileExt(Application->ExeName, ".ini"));
                ini -> WriteInteger("Settings", "mvRight", mvRight);
                ini -> WriteInteger("Settings", "mvLeft", mvLeft);
                ini -> WriteInteger("Settings", "jump", jump);
                delete ini;
        }
}
//---------------------------------------------------------------------------

void __fastcall TForm1::FactorySettingsMouseEnter(TObject *Sender)
{
        FactorySettings -> Caption = "< Przywróæ domyœlne >";
}
//---------------------------------------------------------------------------

void __fastcall TForm1::FactorySettingsMouseLeave(TObject *Sender)
{
        FactorySettings -> Caption = "Przywróæ domyœlne";
}
//---------------------------------------------------------------------------


