//---------------------------------------------------------------------------

#ifndef Unit1H
#define Unit1H
//---------------------------------------------------------------------------
#include <Classes.hpp>
#include <Controls.hpp>
#include <StdCtrls.hpp>
#include <Forms.hpp>
#include <ExtCtrls.hpp>
#include <Graphics.hpp>
#include <jpeg.hpp>
#include <ComCtrls.hpp>
//---------------------------------------------------------------------------
class TForm1 : public TForm
{
__published:	// IDE-managed Components
        TImage *LeftWall;
        TImage *Background;
        TImage *RightWall;
        TLabel *StartGame;
        TImage *Title;
        TLabel *Highscores;
        TLabel *Options;
        TLabel *Exit;
        TLabel *Subtitle;
        TImage *Wloszek;
        TImage *Kapi;
        TImage *Severian;
        TImage *Trojan;
        TImage *NadakaN;
        TImage *Bulgar;
        TLabel *Return;
        TImage *Platform6;
        TImage *Platform5;
        TImage *Platform4;
        TImage *Platform3;
        TImage *Platform2;
        TImage *Platform1;
        TImage *Ground;
        TTimer *MovingLeft;
        TTimer *MovingRight;
        TTimer *Jumping;
        TTimer *Falling;
        TTimer *GameControl;
        TTimer *GameTime;
        TLabel *ScoreTitle;
        TLabel *Score;
        TLabel *TimeTitle;
        TLabel *Time;
        TImage *SpeedBonus;
        TImage *Character;
        TLabel *GameReset;
        TLabel *GameClose;
        TLabel *Option1Title;
        TLabel *Option2Title;
        TLabel *Option3Title;
        TLabel *Option1;
        TLabel *Option2;
        TLabel *Option3;
        TLabel *FactorySettings;
        TLabel *FirstPlace;
        TLabel *SecondPlace;
        TLabel *ThirdPlace;
        TLabel *FourthPlace;
        TLabel *FifthPlace;
        TLabel *SixthPlace;
        TLabel *SeventhPlace;
        TLabel *EighthPlace;
        TLabel *NinthPlace;
        TLabel *TenthPlace;
        TLabel *Information;
        TLabel *UserNickname;
        void __fastcall ExitClick(TObject *Sender);
        void __fastcall StartGameClick(TObject *Sender);
        void __fastcall HighscoresClick(TObject *Sender);
        void __fastcall OptionsClick(TObject *Sender);
        void __fastcall StartGameMouseEnter(TObject *Sender);
        void __fastcall StartGameMouseLeave(TObject *Sender);
        void __fastcall HighscoresMouseEnter(TObject *Sender);
        void __fastcall HighscoresMouseLeave(TObject *Sender);
        void __fastcall OptionsMouseEnter(TObject *Sender);
        void __fastcall OptionsMouseLeave(TObject *Sender);
        void __fastcall ExitMouseEnter(TObject *Sender);
        void __fastcall ExitMouseLeave(TObject *Sender);
        void __fastcall ReturnClick(TObject *Sender);
        void __fastcall ReturnMouseEnter(TObject *Sender);
        void __fastcall ReturnMouseLeave(TObject *Sender);
        void __fastcall WloszekClick(TObject *Sender);
        void __fastcall KapiClick(TObject *Sender);
        void __fastcall SeverianClick(TObject *Sender);
        void __fastcall TrojanClick(TObject *Sender);
        void __fastcall NadakaNClick(TObject *Sender);
        void __fastcall BulgarClick(TObject *Sender);
        void __fastcall MovingLeftTimer(TObject *Sender);
        void __fastcall MovingRightTimer(TObject *Sender);
        void __fastcall JumpingTimer(TObject *Sender);
        void __fastcall FallingTimer(TObject *Sender);
        void __fastcall GameTimeTimer(TObject *Sender);
        void __fastcall GameControlTimer(TObject *Sender);
        void __fastcall FormKeyDown(TObject *Sender, WORD &Key,
          TShiftState Shift);
        void __fastcall FormKeyUp(TObject *Sender, WORD &Key,
          TShiftState Shift);
        void __fastcall GameResetClick(TObject *Sender);
        void __fastcall GameResetMouseLeave(TObject *Sender);
        void __fastcall GameCloseClick(TObject *Sender);
        void __fastcall GameCloseMouseLeave(TObject *Sender);
        void __fastcall GameResetMouseEnter(TObject *Sender);
        void __fastcall GameCloseMouseEnter(TObject *Sender);
        void __fastcall Option1Click(TObject *Sender);
        void __fastcall Option2Click(TObject *Sender);
        void __fastcall Option3Click(TObject *Sender);
        void __fastcall Option1MouseEnter(TObject *Sender);
        void __fastcall Option1MouseLeave(TObject *Sender);
        void __fastcall Option2MouseEnter(TObject *Sender);
        void __fastcall Option2MouseLeave(TObject *Sender);
        void __fastcall Option3MouseEnter(TObject *Sender);
        void __fastcall Option3MouseLeave(TObject *Sender);
        void __fastcall FactorySettingsClick(TObject *Sender);
        void __fastcall FactorySettingsMouseEnter(TObject *Sender);
        void __fastcall FactorySettingsMouseLeave(TObject *Sender);
private:	// User declarations
        int platformsFallingSpeed, charackterFallingSpeed, jumpHeight, jumpSpeed;
        int seconds, timeThreshold, counter, platformsPoints, place;
        unsigned long int scoreboard[10], score;
        AnsiString nicknames[10], temp;
        bool fallingStart;
        WORD mvLeft, mvRight, jump;
public:		// User declarations
        __fastcall TForm1(TComponent* Owner);
        void setValues();
        void hideMenu();
        void showMenu();
        void gameplayON();
        void gameplayOFF();
        void setKeyCaption(TLabel *Option, WORD *UserKey);
        void setHighscores();
};
//---------------------------------------------------------------------------
extern PACKAGE TForm1 *Form1;
//---------------------------------------------------------------------------
#endif
