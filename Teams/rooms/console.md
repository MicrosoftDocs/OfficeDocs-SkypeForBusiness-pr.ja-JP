---
title: Microsoft Teams ミーティングのコンソールを構成する
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: この記事では、Microsoft Teams ミーティングのコンソールとその周辺機器の設定および構成方法を説明します。
ms.openlocfilehash: d5c1b7f47769d925f6d67527429971970b555044
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905449"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Microsoft Teams ミーティングのコンソールを構成する

この記事では、Microsoft Teams ミーティングのコンソールとその周辺機器の設定方法を説明します。
  
これらの手順は、「[デプロイの概要](rooms-deploy.md)」で説明されているように、必要な Microsoft Teams アカウントや Skype for Business のアカウントと Exchange アカウントが既に作成されている場合にのみ実行してください。 「[Microsoft Teamsミーティングの要件](requirements.md)」で説明されているハードウェアとソフトウェアが必要になります。 このトピックには次のセクションが含まれます。
  
- [インストール メディアを準備する](console.md#Prep_Media)
- [コンソールにプライベート CA 証明書をインストールする](console.md#Certs)
- [Windows 10 と Microsoft Teams ミーティングのコンソール アプリをインストールする](console.md#Reimage)
- [コンソールの初期設定](console.md#Initial)
- [Microsoft Teams ミーティングのデプロイ チェックリスト](console.md#Checklist)

> [!NOTE]
> Microsoft Teams ミーティングは、「[デプロイの概要](rooms-deploy.md)」で説明されているとおりにデバイス アカウントが正しく設定されている、適切に構成された Microsoft Teams 環境または Skype for Business 環境でのみ動作します。
  
## <a name="prepare-the-installation-media"></a>インストール メディアを準備する
<a name="Prep_Media"> </a>

Microsoft Teams ミーティングのコンソール アプリをインストールするには、少なくとも 32GB の容量がある USB 記憶装置が必要です。 このデバイスには他のファイルが存在しないようにする必要があります。この USB ストレージ上の既存のファイルはすべて失われます。
  
> [!NOTE]
> 記載されている説明に従って Microsoft Teams ミーティングのインストール メディアを作成しないと、予期しない動作が発生する可能性があります。

> [!NOTE]
> 次の手順で、新しい Microsoft Teams ミーティング デバイスのイメージを作成するためにインストール メディアを作成する方法を説明します。 既定では、既存のデバイスは Windows Update および Windows ストアから自動的に更新されます。

> [!IMPORTANT]
> Microsoft Teams ミーティングのインストール メディアを作成するために使用する Windows 10 コンピューターは、ターゲット インストール メディアと同じか、それ以降のバージョンの Windows で動作している必要があります。
  
1. [CreateSrsMedia.ps1 スクリプト](https://go.microsoft.com/fwlink/?linkid=867842)をダウンロードします。
2. Windows 10 コンピューターの管理者特権でのプロンプトから CreateSrsMedia.ps1 スクリプトを実行します。
3. スクリプトの指示に従って、Microsoft Teams ミーティング USB セットアップ ディスクを作成します。


> [!TIP]
> CreateSrsMedia.ps1 が起動されるたびに、画面出力にはそのセッションのログ ファイル名かトランスクリプト名が表示されます。 スクリプトの実行で問題が発生した場合は、サポートを要求するときに、そのトランスクリプトのコピーを使用できるようにしておいてください。 

CreateSrsMedia.ps1 スクリプトを実行すると、次のタスクが自動化されます。

1. Microsoft Teams ミーティング用の最新の MSI インストーラーをダウンロードする。
2. ユーザーが提供する必要のある Windows のビルドを判別する。 最新のリリース版は、Microsoft Teams ミーティング デバイスで使用するためのテストやサポートがなされていない場合があります。
3. 必要なサポート コンポーネントをダウンロードする。
4. 必要なコンポーネントをインストール メディアにアセンブルする。

特定のバージョンの Windows 10 が必要です。このバージョンはボリューム ライセンスのお客様のみが利用できます。  [ボリューム ライセンス サービス センター](https://www.microsoft.com/Licensing/servicecenter/)からコピーを入手できます。

完了したら、コンピューターから USB ディスクを削除し、「[Windows 10 と Microsoft Teams ミーティングのコンソール アプリをインストールする](console.md#Reimage)」に進みます。

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Windows 10 と Microsoft Teams ミーティング コンソール アプリをインストールする
<a name="Reimage"> </a>

ここで、作成したセットアップ メディアを適用する必要があります。 ターゲット デバイスは、アプライアンスとして実行されます。既定のユーザーは Microsoft Teams ミーティング コンソール アプリのみを実行するように設定されます。

1. ターゲット デバイスがドック (Surface Pro など) にインストールされている場合は、ドックとの接続を解除します。

2. ターゲット デバイスがネットワークに接続されていないことを確認します。

3. ターゲット デバイスが AC 電源に接続されていることを確認します。

4. USB セットアップ ディスクをターゲット デバイスに差し込みます。

5. USB セットアップ ディスクにブートします。 製造元の手順を参照してください。 ターゲット デバイスが Surface Pro の場合は、次の手順を使用して USB セットアップ ディスクにブートします。

    a. ボリューム ダウン (-) ボタンを押したままにします。

    b. 電源ボタンを押して、離します。

    c. Windows セットアップが起動したら、ボリューム ダウン (-) ボタンを離します。

8. インストールが完了すると、システムがシャットダウンします。
    
システムがシャット ダウンしたら、USB セットアップ ディスクを安全に取り外すことができます。 これで、ターゲット デバイスをドックに設置して (ドックベースの製品を使用している場合)、会議室に必要な周辺機器を取り付け、ネットワークに接続することができます。 製造元の手順を参照してください。

> [!NOTE]
> Microsoft Teams ミーティングのソフトウェア更新プログラムは、ビジネス向け Microsoft Store から自動的にダウンロードされます。 会議室コンソールがストアにアクセスして自己更新できるかどうかを確認するには、「[ビジネスおよび教育機関向け Microsoft Store の前提条件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)」を参照してください。  

### <a name="selecting-a-language"></a>言語の選択 

Creators Update では、暗黙的に言語を選択するとアプリケーションの言語がユーザーが希望する言語に設定されない場合 (フランス語でコンソール アプリを表示したいのに英語で表示される場合など)、ApplyCurrentRegionAndLanguage.ps1 スクリプトを使用する必要があります。
  
> [!NOTE]
> 次の手順は、Windows Creators Update を使用して作成されたコンソールにのみ使用できます。 新しいプロビジョニング システムを使用するメディアを使用してセットアップされていないレガシ システムや現行のシステムでは次の手順は使用できません。ただし、この手動操作が必要となる最初の問題の影響を受けないようにする必要もあります (Anniversary Edition では、セットアップの一部としてアプリの言語を明示的に選択できます)。
  
### <a name="to-apply-your-desired-language"></a>必要な言語を適用するには

1. 管理モードに切り替えます。
    
2. [スタート] メニューを選択します。
    
3. ギア アイコンを選択して [**設定**] アプリを起動します。
    
4. **[時刻 &amp; 言語]** を選択します。
    
5. **[地域 &amp; 言語]** を選択します。
    
6. [**言語の追加**] を選択します。
    
7. 追加する言語を選択します。
    
8. [言語] 一覧に追加した言語を選択します。
    
9. [**既定に設定**] を選択します。
    
10. 削除する言語については、次の操作を行います。
    
    a. 削除する言語を選択します。
    
    b. [**削除**] を選択します。
    
11. 管理者特権でコマンド プロンプトを開始します。
    
12. 次のコマンドを実行します。 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. システムを再起動します。
    
これで、目的の言語が Microsoft Teams ミーティングのコンソールに適用されます。
## <a name="initial-set-up-of-the-console"></a>コンソールの初期設定
<a name="Initial"> </a>

Windows をインストールすると、次回 Microsoft Teams ミーティングのコンソール アプリを起動するか、/reboot オプションが選択されていた場合、アプリの初期設定プロセスが実行されます。
  
1. [ユーザー アカウント] 画面が表示されます。 コンソールで使用される会議室アカウントの Skype サインイン アドレス ("ユーザー@ドメイン" 形式) を入力します。
    
2. 会議室アカウントのパスワードを入力し、確認のためにもう一度入力します。
    
3. [Configure Domain](ドメインの設定) で、Skype for Business Server の FQDN を設定します。 Skype for Business SIP ドメインがユーザーの Exchange ドメインと異なる場合は、このフィールドに Exchange ドメインを入力します。
    
4. **[次へ]** をクリックします。
    
5. [機能] 画面に表示されたデバイスを選択して、**[次へ]** をクリックします。 既定では、自動画面共有はオンで、会議名の非表示はオフになっています。 選択対象のデバイスは次のとおりです。
    
   - 会議用のマイク: 会議室で使用する既定のマイク。
    
   - 会議用のスピーカー: 会議で使用する既定のスピーカー。 
    
   - 既定のスピーカー: HDMI インジェストからのオーディオ用に使用されるスピーカー。
    
     それぞれの項目に、選択できるドロップダウン メニューのオプションがあります。各デバイスについて選択を行う必要があります。
    
6. [**完了**] をクリックします。
    
Microsoft Teams ミーティングのコンソール アプリは、先ほど入力した資格情報を使用して Skype for Business Server へのサインインを直ちに開始し、同じ資格情報を使用して Exchange との予定表の同期も開始します。 コンソール アプリの使用方法の詳細については、「[Microsoft Teams ミーティングのヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)」を参照してください。
  
> [!IMPORTANT]
> Microsoft Teams ミーティングには、認定されたコンソール ハードウェアが必要です。 Microsoft Teams ミーティングのコンソール アプリを含むイメージが正しく作成されていても、コンソール ハードウェアが検出されない限り、そのイメージは初期設定手順の後に起動しません。 Surface Pro ベースのソリューションの場合、このチェックが成功するには、Surface Pro と付属するドック ハードウェアが接続されている必要があります。
  
> [!NOTE]
> ユーザーが英語以外の言語を使用する場合、タッチ キーボードでは記号がサポートされておらず、初期設定の際に物理キーボードをコンソールに接続することが必要になることがあります。
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>コンソールにプライベート CA 証明書をインストールする
<a name="Certs"> </a>

Microsoft Teams ミーティングのコンソールは、接続先のサーバーで使用されている証明書を信頼する必要があります。 O365 の場合、これらのサーバーでは公的証明機関が使用され、Windows 10 によって自動的に信頼されるため、この処理は自動的に実行されます。 Active Directory や Windows 証明機関を使用したオンプレミス デプロイなど、民間の証明機関を使用する場合は、Microsoft Teams ミーティングのコンソールに次の 2 つの方法で証明書を追加できます。
  
- 証明機関が Active Directory に対して公開されている場合 (通常のデプロイ オプション)、コンソールを Active Directory に参加させると、必要な証明書は自動的に追加されます。
    
- イメージング プロセスの後で、証明書を手動でインストールできます。 この操作を行う前に、[コンソールの初期設定](console.md#Initial)を完了する必要があります。
    
### <a name="to-manually-install-the-certificate"></a>証明書を手動でインストールするには 

1. CA 証明書をお使いのコンピューターにダウンロードして、C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer に保存します。
    
2. コンソールを管理者モードにします (「[管理者モードとデバイス管理](rooms-operations.md#AdminMode)」を参照してください)。
    
3. 次のコマンドを実行します。
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Active Directory ドメインに参加する (オプション)
<a name="Certs"> </a>

Microsoft Teams ミーティングのコンソールをドメインに参加させることができます。 Microsoft Teams ミーティングのコンソールは、使用する PC ワークステーションとは別の OU に配置する必要があります。これは、多くのワークステーション ポリシーは Microsoft Teams ミーティングと互換性がないためです。 たとえば、パスワードの強制ポリシーが設定されていると、Microsoft Teams ミーティングは自動的に起動しなくなります。 GPO 設定の管理の詳細については、「[Microsoft Teams ミーティングの管理](rooms-operations.md)」を参照してください。
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Microsoft Teams ミーティングをドメインに参加させるには

1. 管理者アカウントからコンソールにサインインします (「[管理者モードとデバイス管理](rooms-operations.md#AdminMode)」を参照してください)。
    
2. 管理者特権で Powershell コマンド プロンプトを起動します。
    
3. Powershell に次のコマンドを入力します。
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

たとえば、完全修飾ドメインが redmond.corp.microsoft.com で、Microsoft Teams ミーティングのコンソールを "Resources" OU の子である "Microsoft Teams Rooms" OU に配置する場合、次のコマンドを実行します。
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 ドメインに参加させるときにコンピューターの名前を変更する場合は、-NewName フラグを使用し、その後にコンピューターの新しい名前を続けます。
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Microsoft Teams ミーティングのデプロイ チェックリスト
<a name="Checklist"> </a>

コンソールとそのすべての周辺機器が完全に構成されていることを最終確認するときは、以下のチェックリストを使用します。
  
**アプリケーションの設定**

|||
|:-----|:-----|
|☐  <br/> |ルーム アカウント名と電話番号 (PSTN が有効な場合) が、コンソール画面の右上に正しく表示される  <br/> |
|☐  <br/> |Windows コンピューター名が正しく設定されている (リモート管理に役立つ)  <br/> |
|☐  <br/> |管理者アカウントのパスワードが設定されており、確認済みである  <br/> |
|☐  <br/> |すべてのファームウェア更新プログラムが適用されている  <br/> |
   
**オーディオ/ビデオ周辺機器**

|||
|:-----|:-----|
|☐  <br/> |カメラ周辺機器のファームウェアのバージョンが正しい (該当する場合)  <br/> |
|☐  <br/> |カメラが機能し、適切に配置されている  <br/> |
|☐  <br/> |既定の再生デバイスと既定の再生通信デバイスの設定が、目的のオーディオ周辺機器に設定されている  <br/> |
|☐  <br/> |既定の録音通信デバイスの設定が目的のオーディオ周辺機器に設定されている  <br/> |
|☐  <br/> |オーディオ周辺機器のファームウェアのバージョンが正しい (該当する場合)  <br/> |
|☐  <br/> |オーディオ入力デバイスが機能し、適切に配置されている  <br/> |
|☐  <br/> |オーディオ出力デバイスが機能し、適切に配置されている  <br/> |
   
**ドック**

|||
|:-----|:-----|
|☐  <br/> |ケーブルが保護されており、圧迫されていない  <br/> |
|☐  <br/> |HDMI を介したオーディオ インジェストが機能している  <br/> |
|☐  <br/> |HDMI を介したビデオ インジェストが機能している  <br/> |
|☐  <br/> |ドックは自由に回転することができる  <br/> |
|☐  <br/> |表示の明るさが環境に適している  <br/> |
   
## <a name="see-also"></a>関連項目
<a name="Checklist"> </a>

[Microsoft Teams ミーティングを計画する](rooms-plan.md)
  
[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)
  
[Microsoft Teams Rooms コンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](rooms-manage.md)
