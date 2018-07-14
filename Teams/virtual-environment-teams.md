---
title: 仮想環境でマイクロソフトのチームを実行します。
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 07/13/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jaym
description: 仮想化環境でマイクロソフトのチームを実行する方法について説明します。
localization_priority: Normal
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08a82c2450d238a59d7e076ceb95368c3dce91e2
ms.sourcegitcommit: 11adc15c5191d7bf6bb37058cae3d54649c25e97
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2018
ms.locfileid: "20363924"
---
<a name="run-microsoft-teams-in-a-virtual-environment"></a>仮想環境でマイクロソフトのチームを実行します。
============================================

この資料では、要件とチームを使用して仮想化された環境での制限事項について説明します。

仮想デスクトップ インフラストラクチャ (VDI) 環境は、非常に高度なセキュリティとコンプライアンスが求められる組織で使用します。 ユーザーは、すべてのデスクトップ アプリケーションやリモート デスクトップ サービスまたはのようなリモート接続を使用してファイルを格納している仮想デスクトップで作業を行います。 アクセスしたり、(ソフトウェア) を追加せずに、ユーザーのローカル デバイス上のオーディオまたはビデオ デバイスを使用して仮想デスクトップ上のチームが最適化されていないため、VDI 環境で作業している通常は通話などのマルチ メディアのシナリオに関連する課題ビデオ通話、画面共有、アプリケーション共有、共同編集などです。 

> [!NOTE]
> 組織が VDI でチームを完全に実行を選択できます (Web アプリケーションまたはデスクトップ クライアントを使用して) がお勧め次のポリシーは、オフにするため、ユーザーでは、仮想化環境に不適切な経験がありません。 これらポリシーの変更を反映するのには時間がかかることに注意してください。 指定したアカウントの変更がすぐに表示されない場合、は、数時間後にもう一度してみてください。 

## <a name="calling"></a>通話

*CsTeamsCallingPolicy*コマンドレットを呼び出すと、プライベートでのオプションを呼び出すかどうかの管理者は、コントロールを有効にして、グループ チャットが有効か無効です。 


|ポリシー名 |説明  |推奨値  |
|---------|---------|---------|
|AllowPrivateCalling   |か通話アプリはチームのクライアントの左側のレールに使用できるかどうかを制御します。 プライベート チャットでの通話や映像通話のオプションを表示するかどうかを制御します。 |**False**とプライベート チャットで通話や映像通話のオプションを削除するのには左側のレールからの通話アプリを削除するには、これを設定します。 |

### <a name="powershell-instructions"></a>PowerShell の指示

1.  管理者として PowerShell を起動します。
2.  Skype オンラインのコネクタに接続します。<br>
\>> *# Office 365 のユーザー名とパスワードを設定します。*<br>
\>> *$username$ ="管理者の電子メール アドレス]*<br>
\>> *$password =「パスワード」を寄せ SecureString-AsPlainText-フォース*<br>
\>> *$LiveCred = 新しいオブジェクトの型名 System.Management.Automation.PSCredential の引き数リスト $username$、$password*<br><br>
\>> *# Skype をオンライン接続します。*<br>
\>> *インポート モジュール SkypeOnlineConnector*<br>
\>> *$sfboSession = New CsOnlineSession-資格情報の $LiveCred*<br>
\>> *インポート-PSSession $sfboSession*<br>
3.  ポリシーのオプションを呼び出すことの一覧を表示します。<br>
\>> *Get CsTeamsCallingPolicy*
4.  呼び出し元のすべてのポリシーが無効になっている、事前に定義されたオプションになります。<br>
![無効になっているすべての会議ポリシーを使用して会議のオプションのスクリーン ショットです。](media/virtual-environment-image2.png)
5.  仮想化環境でチームを使用するすべてのユーザーに"DisallowCalling"の事前に定義されたポリシーのオプションが適用されます。<br>
\>> *AllOff を与える CsTeamsMeetingPolicy グループのユーザー電子メール id の Id*

## <a name="meetings"></a>会議

*CsTeamsMeetingPolicy*コマンドレットは、ユーザーが作成したミーティングや会議中にアクセスできる機能の種類を制御する管理者を有効にします。 匿名または外部のユーザーとの会議の処理方法を決定することもできます。

|ポリシー名 |説明  |推奨値  |
|---------|---------|---------|
|AllowPrivateMeetingScheduling    |ユーザーが秘密の会議をスケジュールできるかどうかを決定します。         |**False を指定**するユーザーの秘密の会議をスケジュールすることを禁止するのには、これを設定します。         |
|AllowChannelMeetingScheduling     |ユーザーはチャネルのミーティングをスケジュールできるかどうかを決定します。         |**False**にチャネルの会議をスケジュールすることを禁止するには、これを設定します。         |
|AllowMeetNow     |ユーザーが作成または、臨時会議を開始できるかどうかを決定します。         |**False**に、臨時会議を開始することを禁止するには、これを設定します。         |
|ScreenSharingMode     |ユーザーが通話や会議での画面を共有する許可は、モードを決定します。         |] に**無効な**ユーザーが、画面を共有することを禁止するのには、これを設定します。         |
|AllowIPVideo     |ユーザーの会議または呼び出しにビデオが有効になっているかどうかを決定します。         |**False**に、ビデオの共有からユーザーを禁止するには、これを設定します。         |
|AllowAnonymousUsersToDialOut     |匿名ユーザーが PSTN 番号にダイアル アウトできるかどうかを決定します。         |**False を指定**する匿名ユーザーが発信することを禁止するには、これを設定します。         |
|AllowAnonymousUsersToStartMeeting     |匿名ユーザーが会議を開始できるかどうかを決定します。         |に**false を指定**して会議を開始することを禁止するには、これを設定します。         |
|AllowOutlookAddIn     |ユーザーが Outlook デスクトップ クライアントでチームのミーティングをスケジュールできるかどうかを決定します。         |**False を指定**すると、ユーザーが Outlook クライアントでのチーム ミーティングをスケジュールすることを禁止するには、これを設定します。         |
|AllowParticipantGiveRequestControl     |参加者が要求または、画面の共有を制御できるようにするかどうかを決定します。         |この設定を**False**に、ユーザーを禁止すること、会議の制御を要求します。         |
|AllowExternalParticipantGiveRequestControl     |外部の参加者が要求または、画面の共有を制御できるようにするかどうかを決定します。         |この設定を**False**に外部ユーザーを禁止すること、会議の制御を要求します。         |
|AllowPowerPointSharing     |ユーザーの会議で PowerPoint の共有を許可するかどうかを決定します。         |に**true を指定**できるようにするには、これを設定します。<br>**False を指定**するユーザーが会議中の PowerPoint ファイルを共有することを禁止するには、これを設定します。         |
|AllowWhiteboard     |ユーザーの会議でホワイト ボードを許可するかどうかを決定します。         |**False**に、会議でホワイト ボード アプリケーションを禁止するには、これを設定します。         |
|AllowTranscription     |ユーザーの会議で、リアルタイムまたは会議後のキャプションおよびトランスクリプションができるかどうかを決定します。         |**False**に議事録と会議でキャプションを禁止するには、これを設定します。         |

### <a name="powershell-instructions"></a>PowerShell の指示

1.  管理者として PowerShell を起動します。
2.  Skype オンラインのコネクタに接続します。<br>
\>> *# Office 365 のユーザー名とパスワードを設定します。*<br>
\>> *$username$ ="管理者の電子メール アドレス]*<br>
\>> *$password =「パスワード」を寄せ SecureString-AsPlainText-フォース*<br>
\>> *$LiveCred = 新しいオブジェクトの型名 System.Management.Automation.PSCredential の引き数リスト $username$、$password*<br><br>
\>> *# Skype をオンライン接続します。*<br>
\>> *インポート モジュール SkypeOnlineConnector*<br>
\>> *$sfboSession = New CsOnlineSession-資格情報の $LiveCred*<br>
\>> *インポート-PSSession $sfboSession*
3.  [ミーティング ポリシーのオプションの一覧を表示:<br>
\>> *Get CsTeamsMeetingPolicy*
4.  会議のすべてのポリシーが無効になっている事前に定義されたオプションになります。<br>
![オプションを無効になっているすべての会議ポリシーを使用して呼び出すことのスクリーン ショットです。](media/virtual-environment-image1.png)
5.  仮想化環境でチームを使用するすべてのユーザーに"AllOff"の事前に定義されたポリシーのオプションが適用されます。<br>
\>> *AllOff を与える CsTeamsMeetingPolicy グループのユーザー電子メール id の Id*

##<a name="known-limitations"></a>既知の制限

以外にも記載されているオーディオとビデオの制限の同は、仮想化環境上のユーザーが直面する可能性がありますいくつか追加の制限があります。

- **他のユーザーによって作成されたミーティングに参加します。** 場合でも、上記のポリシーでは、ユーザーが会議の作成を制限では、他のユーザーによって送信された会議に参加することができます。 これらの会議でホワイト ボードを使用して、ビデオを共有する機能とかどうか管理者それらを無効にしない、または [その他の機能によって異なります。

- **関連する問題では、コンテンツがキャッシュされます。** チームが実行されている仮想環境が永続化されていないかどうか (データがクリーンアップ各ユーザー セッションの終了時)、ユーザーがクライアントのすべてのコンテンツをかどうかに関係なく、もう一度再ダウンロードすることによるパフォーマンスの低下に気付く可能性があります特定のユーザー前のセッションで同じコンテンツにアクセスします。 FSLogix で提供されるよう、移動のキャッシュ ソリューションを使用して、パフォーマンスへの影響を軽減できます。

チームが仮想デスクトップ環境で使用するため最適化された後、管理者はこれらのポリシーを元に戻すし、通常どおりには、チームを使用するユーザーを許可します。

         
        
        
        
        
        
        
        
        
        
        


