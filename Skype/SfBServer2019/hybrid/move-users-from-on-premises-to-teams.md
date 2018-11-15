---
title: 移動ユーザーがチームを設置
ms.author: crowe
author: CarolynRowe
manager: serdars--
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: '概要: は、ユーザー設定を移行し、チームにユーザーを移動する方法を説明します。'
ms.openlocfilehash: af0867bfdc2e12a248baf7cc07746845154d27fd
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26533142"
---
# <a name="move-users-from-on-premises-to-teams"></a>移動ユーザーがチームを設置

ビジネス サーバー 2019 の Skype では、チームがこの資料で説明したように、オンプレミス ユーザーを移行できます。

注意してくださいチームにユーザーを移動した後です。 
 
- 会議は、ビジネス オンラインでは、Skype に移行し、その連絡先は、チームに移行します。 
- Skype のビジネスのリッチ クライアント (ユーザーの求められませんサインインするたびに)、または (1 回だけダウンロードしてサインインする必要があります) Skype 会議アプリケーションを通じて、Skype の会議に参加することができます。 ユーザーは、Skype のチーム内でのビジネス会議のリンクをクリックすると、会議が適切なアプリケーションの起動します。

- 携帯電話] で、ユーザーは既存の Skype のネイティブのアプリケーションだけを使用してビジネス ・ ミーティングに参加することになります。

> [!NOTE]
> TeamsOnly モードにユーザーを移動すると後、は、オンライン ビジネスの Skype のユーザーが配置されています。

## <a name="prerequisites-for-moving-on-premises-users-to-teams"></a>オンプレミス ユーザーをチームに移動するための前提条件 

このセクションでは、オンプレミス ユーザーをチームに移動するための前提条件について説明します。 しなきゃいけません：
- [ハイブリッド接続の設定](#set-up-hybrid-connectivity)(まだ行っていないため) 場合
- [チームへの移行のユーザーに通知](#notify-your-users-of-the-move-to-teams)(省略可能)
- [ユーザーが有効なライセンスを持っていることを確認します。](#make-sure-your-users-have-a-valid-license)
- [音声の構成要件に注意してください。](#voice-configuration-requirements)
- [チームのアップグレード ・ ポリシーを設定](#assign-a-teams-upgrade-policy)(省略可能)

## <a name="set-up-hybrid-connectivity"></a>ハイブリッド接続を設定します。
されていない場合に、ユーザーを移行する前に、ビジネス オンラインの Skype、Skype ビジネス サーバー設置環境の間のハイブリッドの接続を構成していることを確認する必要があります。 ハイブリッド接続は、Active Directory の同期など、フェデレーションを構成する必要があります。 詳細については、[ハイブリッドの接続を計画](plan-hybrid-connectivity.md)し、[ハイブリッド接続の構成](configure-hybrid-connectivity.md)を参照してください。

## <a name="notify-your-users-of-the-move-to-teams"></a>チームへの移行のユーザーに通知します。 
これは、いずれかを考慮する必要がありますが、オプションの手順です。 チームの保留中のアップグレードをユーザーに通知、設置型の TeamsUpgradePolicy、TeamsUpgradeConfiguration コマンドレットを使用します。 (Win32 クライアントのみ) をアップグレードする前にバック グラウンドでサイレントのチームの自動ダウンロードを構成することもできます。 

などのチームにアップグレード中は、ユーザーに通知をするには、-NotifySbUser パラメーターを使用して設置 TeamsUpgradePolicy コマンドレットを使用します。 グローバル、サイト、プール、またはユーザー レベルでポリシーを設定できます。 次のコマンドを作成し、ユーザー レベル ポリシーを付与します。
 
```
New-CsTeamsUpgradePolicy -Identity UpgradeNotice -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity user01 -PolicyName “UpgradeNotice”
```

Get csTeamsUpgradePolicy コマンドレットを使用して、このポリシーを確認できます。

間もなくチームへの移行の通知がユーザーに表示します。 通知は、(適切なバージョン) と、Win32、Mac、モバイル、および Web クライアントで発生します。

(Win32 クライアント) のチームの DownloadTeams パラメーターを使用してオンプレミス TeamsUpgradeConfiguration コマンドレットを使用して、アップグレード中のユーザーの自動ダウンロードを指定することができます。 テナント レベルでは、このポリシーを設定して、グローバル、サイトに適用することができ、レベルをプールします。 たとえば、次のコマンドでは、サイト レベルでポリシーを設定します。

```
New-CsTeamsUpgradeConfiguration -Identity “site:redmond1” 
```

既定では、DownloadTeams の値は true の場合、ですが、NotifySfbUser を特定のユーザーのチームを有効にする場合は True に設定することもする必要があります。 

## <a name="make-sure-your-users-have-a-valid-license"></a>ユーザーが有効なライセンスを持っていることを確認します。  
移行する前に、オンプレミス ユーザー必要がある有効なライセンスでは、次のように。

-   チームのライセンスが必要です。
-   ユーザーがオンプレミス エンタープライズ VoIP を使用するように構成されている場合を移動するとき、オンラインでのボイスのライセンスが必要です。 
-   設置型では、ダイヤルイン会議のユーザーを構成する場合 (クラウド PBX) の電話システムのライセンスが必要です。

## <a name="voice-configuration-requirements"></a>音声の構成要件

オンプレミス ユーザーが設置型の音声を使用している場合、2 つのオプションがあります。

-  **テレフォニー機能を持つユーザーを移行します。** ユーザーとチームのクライアントを使用して呼び出しを受信できます。  Microsoft の計画を呼び出すか、直接ルーティングではチームに、テレフォニー サービスを接続するを選択することができます。  

    -  クラウドをすべて音声ソリューションを提供する Microsoft の計画を呼び出します。 Microsoft の計画を呼び出すことの詳細については、(リンク準備中) を参照してください。 
    -  直接ルーティングでは、事実上、PSTN トランクを使用することができ、お客様が所有する電話装置とマイクロソフトの電話システムとの間の相互運用性を構成することができます。  詳細については、[直接ルーティングを計画](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan)し、[直接ルーティングの構成](https://docs.microsoft.com/MicrosoftTeams/direct-routing-configure)を参照してください。

-  **テレフォニー機能のないユーザーを移行します。** テレフォニー機能を維持せずにユーザーを移行する場合は、ユーザーは、クラウドで適切なライセンスを持っていることを確認してください。 

## <a name="assign-a-teams-upgrade-policy"></a>チームのアップグレード ・ ポリシーを設定します。  
着信メッセージと呼び出しのルーティングを制御するのにようにユーザー ポリシーを管理するのには、オンライン ツールを使用できます。 詳細については、(リンク準備中) を参照してください。

## <a name="move-on-premises-users-to-teams"></a>オンプレミス ユーザーをチームに移動します。

PowerShell コマンドレットを使用するか、ビジネス サーバー 2019 のコントロール パネルの Skype を使用して、チームに、オンプレミスのユーザーを移動できます。

### <a name="move-users-by-using-powershell"></a>PowerShell を使用してユーザーの移動
チームにユーザーを移動するには、PowerShell を使用して、コマンドレットを使用する移動 CsUser moveToTeams パラメーターを使用して次のように。

```
Move-CsUser -Identity user0 -Target sipfed.online.lync.com -moveToTeams -credentials $cred. 
```

($cred = 資格情報の取得。 入力してください Office 365 管理者の資格情報です。)

> [!NOTE]
> このコマンドは、TeamsOnly モードを TeamsUpgradePolicy を設定します。 
 
チームへの移行が成功した後、ビジネス クライアント用のユーザーの Skype には、次のメッセージが表示されます。 

![チーム メッセージ移行に成功しました](../media/teams-upgrade-complete-message.png)

ビジネス用の Skype がミーティングに参加する以外のユーザーに利用可能な不要になったされることに注意します。 

まれに、チームにユーザーを移動する場合、ダイヤルイン会議をオーバーライドし、音声機能をクラウドにする場合があります。 Csuser からの移動コマンドを使用して次のパラメーターを使用してこれを行うことができます。
- **BypassAudioConferencingCheck:** ユーザーのダイヤルイン会議機能を備えた、設置型の場合は、ユーザーには、AudioConf ライセンスを移行する前に Office 365 に割り当てられている必要があります。 クラウドへの移行、ユーザーがクラウドでの音声会議を準備します。 場合は、何らかの理由により、ユーザーをクラウドに移動するが、音声会議機能を使用するは、このパラメーターを指定することによってオーバーライドできます。
- **ByPassEnterpriseVoice:** ユーザーのエンタープライズ VoIP の設置型の有効な場合は、ユーザーに Office 365 に移行する前に割り当てられたエンタープライズ VoIP のライセンスは必要です。 クラウドへの移行後の雲の中の音声をユーザーが準備されます。 場合は、何らかの理由により、ユーザーをクラウドに移行するが、クラウドの音声機能を使用して、このパラメーターを指定することでクラウドの音声をオーバーライドできます。
 
### <a name="move-users-by-using-the-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、ユーザーの移動 

チームにユーザーを移動するには、ビジネス コントロール パネルに、Skype を使用します。

1. ビジネス コントロール パネルの Skype を開くし、Office 365 アカウントにサインインします。

2. 左側のナビゲーションでは、**ユーザー**を選択し、移行するユーザーを選択します。 
     
3. [**操作**] メニューで、**チームを選択したユーザーの移動**を選択します。 

    ![移行を確認するのには次へをクリックすると](../media/migration-confirmation.png)
    
4. [**次**への移行を確認] をクリックします。 

チームにユーザーを移動すると後、は、次のような確認が表示されます。

![移動ユーザーの確認](../media/move-user-confirmation.png)
<br/><br/>
![ユーザーが移動されているメッセージ](../media/users-moved-successfully.png)

移動が正常に終了しない場合は、次のようなメッセージが表示されます。

![メッセージにユーザーを移動できませんでした](../media/users-not-moved.png)
