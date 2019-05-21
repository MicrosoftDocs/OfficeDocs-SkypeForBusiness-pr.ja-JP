---
title: Microsoft Teams 室コンソールを構成する
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: この記事では、Microsoft Teams のルーム本体とその周辺機器を設定する方法について説明します。
ms.openlocfilehash: c2513bbd86e2754c2e1008195ca1cc050a118882
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306535"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Microsoft Teams 室コンソールを構成する

この記事では、Microsoft Teams のルーム本体とその周辺機器を設定する方法について説明します。
  
以下の手順は、「 [Microsoft Teams ルームの展開](room-systems-v2.md)」の説明に従って、必要な Microsoft teams または Skype for Business および Exchange アカウントが既に作成およびテストされている場合にのみ実行してください。 [Microsoft Teams の会議室の要件](requirements.md)について説明されているハードウェアとソフトウェアが必要です。 このトピックには次のセクションが含まれます。
  
- [インストールメディアを準備する](console.md#Prep_Media)
- [プライベート CA 証明書をコンソールにインストールする](console.md#Certs)
- [Windows 10 と Microsoft Teams のルームコンソールアプリをインストールする](console.md#Reimage)
- [本体の初期設定](console.md#Initial)
- [Microsoft Teams のルーム展開のチェックリスト](console.md#Checklist)

> [!NOTE]
> Microsoft Teams のルームは、適切に構成された Microsoft Teams または Skype for Business 環境でのみ機能します。ここでは、「 [Microsoft Teams ルームを展開](room-systems-v2.md)する」の説明に従って、デバイスアカウントが正しく設定されています。
  
## <a name="prepare-the-installation-media"></a>インストールメディアを準備する
<a name="Prep_Media"> </a>

Microsoft Teams のルームコンソールアプリをインストールするには、少なくとも 32 GB の容量を備えた USB ストレージデバイスが必要です。 デバイスにその他のファイルは存在しません。USB ストレージ上の既存のファイルは失われます。
  
> [!NOTE]
> この手順に従って Microsoft Teams ルームのインストールメディアを作成しても、予期しない動作が発生する可能性があります。

> [!NOTE]
> 次のプロセスは、新しい Microsoft Teams 室のデバイスにイメージを追加するインストールメディアを作成することです。 既定では、既存のデバイスは、Windows Update と Windows ストアから自動的に更新されます。
  
1. メディアのロードスクリプトをダウンロードします[。](https://go.microsoft.com/fwlink/?linkid=867842)
2. Windows 10 マシン上で管理者特権でのプロンプトから CreateSrsMedia.ps1 スクリプトを実行します。
3. スクリプトの手順に従って、Microsoft Teams の会議セットアップディスクを作成します。


> [!TIP]
> 表示されるのは、"/ファイルの記録" というスクリプトが起動するたびに、画面出力には、そのセッションのログファイルまたはトランスクリプトの名前が含まれます。 スクリプトの実行で問題が発生した場合は、サポートのリクエスト時にそのトランスクリプトのコピーが入手可能であることを確認してください。 

このスクリプトは、次のタスクを自動化します。

1. Microsoft Teams ルーム用の最新の MSI インストーラーをダウンロードします。
2. ユーザーが指定する必要がある Windows のビルドを確認します。 最新のリリース版は、Microsoft Teams 室のデバイスでの使用が、テストおよびサポートされていない可能性があります。
3. 必要なサポートコンポーネントをダウンロードします。
4. インストールメディアで必要なコンポーネントを組み立てます。

Windows 10 の特定のバージョンが必要です。このバージョンはボリュームライセンスのお客様のみが利用できます。  [ボリュームライセンスサービスセンター](https://www.microsoft.com/Licensing/servicecenter/)からコピーを取得できます。

完了したら、コンピューターから USB ディスクを取り出して、「 [Windows 10 と Microsoft Teams のルームコンソールアプリをインストール](console.md#Reimage)する」に進みます。

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Windows 10 と Microsoft Teams のルームコンソールアプリをインストールする
<a name="Reimage"> </a>

作成したセットアップメディアを適用する必要があります。 ターゲットデバイスはアプライアンスとして実行され、既定のユーザーは Microsoft Teams 室コンソールアプリのみを実行するように設定されます。

1. ターゲットデバイスが dock (Surface Pro など) に装着されている場合は、dock から接続を切断します。

2. ターゲットデバイスがネットワークに接続されていないことを確認します。

3. ターゲットデバイスが AC 電源に接続されていることを確認します。

4. USB セットアップディスクをターゲットデバイスに接続します。

5. USB セットアップディスクを起動します。 製造元の指示を参照してください。 ターゲットデバイスが Surface Pro である場合は、次の手順を使用して USB セットアップディスクを起動します。

    a. [音量を下げる] (-) ボタンを押し続けます。

    b. 電源ボタンを押してから離します。

    c. Windows セットアップが起動したら、ボリューム ダウン (-) ボタンを離します。

8. インストールが完了すると、システムはシャットダウンします。
    
システムがシャットダウンされたら、USB セットアップディスクを削除しても安全です。 この時点で、ドックにターゲットデバイスを配置し (dock ベースの製品を使用している場合)、会議室に必要な周辺機器を接続し、ネットワークに接続することができます。 製造元の指示を参照してください。
  
### <a name="selecting-a-language"></a>言語の選択 

Creator の更新では、暗黙的な言語の選択によって、ユーザーが実際のアプリケーション言語を使用していない場合 (たとえば、コンソールアプリをフランス語で起動する必要がある場合)、ApplyCurrentRegionAndLanguage. ps1 スクリプトを使用する必要があります。これは英語で提供されています)。
  
> [!NOTE]
> 次の手順は、Windows Creator の更新プログラムを使用して作成されたコンソールでのみ機能します。 新しいプロビジョニングシステムでメディアを使用して設定していないレガシー/市場システムでは、これらの手順を使用することはできませんが、この手動介入が必要な初期の問題には影響しません。また、セットアップの一部として明示的にアプリの言語。
  
### <a name="to-apply-your-desired-language"></a>必要な言語を適用するには

1. 管理モードに切り替えます。
    
2. [スタート] メニューを選択します。
    
3. ギア アイコンを選択して [**設定**] アプリを起動します。
    
4. [**時刻&amp;の言語**] を選択します。
    
5. [**地域&amp;の言語**] を選択します。
    
6. [**言語の追加**] を選択します。
    
7. 追加する言語を選択します。
    
8. [言語] リストに追加した言語を選択します。
    
9. [**既定に設定**] を選択します。
    
10. 削除する言語については、次の操作を行います。
    
    a. 削除する言語を選択します。
    
    b. [**削除**] を選択します。
    
11. 管理者特権でコマンド プロンプトを開始します。
    
12. 次のコマンドを実行します。 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. システムを再起動します。
    
目的の言語が Microsoft Teams のルームコンソールに適用されるようになりました。
## <a name="initial-set-up-of-the-console"></a>本体の初期設定
<a name="Initial"> </a>

Windows をインストールした後、Microsoft Teams のルームコンソールアプリは、次に起動したとき、または/reboot オプションが選択されたときに、初期セットアッププロセスに進みます。
  
1. [ユーザー アカウント] 画面が表示されます。 コンソールで使用する会議室アカウントの Skype サインインアドレス (user @ domain format) を入力します。
    
2. ルーム アカウントのパスワードを入力し、確認のためにもう一度入力します。
    
3. [ドメインの構成] で、Skype for Business Server の FQDN を設定します。 Skype for Business SIP ドメインがユーザーの Exchange ドメインと異なる場合は、このフィールドに Exchange ドメインを入力します。
    
4. [ **次へ**] をクリックします。
    
5. [機能] 画面で指示されたデバイスを選択し、[**次へ**] をクリックします。 既定では、自動画面共有はオンで、会議名の非表示はオフになっています。 選択対象のデバイスは次のとおりです。
    
   - 会議用のマイク: 会議室で使用する既定のマイク。
    
   - 会議用のスピーカー: 会議で使用する既定のスピーカー。 
    
   - 既定のスピーカー: HDMI インジェストからのオーディオ用に使用されるスピーカー。
    
     それぞれの項目に、選択できるドロップダウン メニューのオプションがあります。各デバイスについて選択を行う必要があります。
    
6. **[完了]** をクリックします。
    
Microsoft Teams のルームコンソールアプリは、上で入力された資格情報を使って Skype for Business Server へのサインインを開始し、同じ資格情報を使用して、予定表の Exchange との同期を開始する必要があります。 コンソールアプリの使い方の詳細については、「 [Microsoft Teams ルームのヘルプ](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)」を参照してください。
  
> [!IMPORTANT]
> Microsoft Teams のルームは、認定された本体のハードウェアの存在に依存します。 Microsoft Teams のルームコンソールアプリが正しく作成された画像も、本体のハードウェアが検出されていない限り、初期セットアップ手順を実行しても起動しません。 Surface Pro ベースのソリューションの場合、このチェックに合格するには、Surface Pro が付随する dock ハードウェアに接続されている必要があります。
  
> [!NOTE]
> 一部の英語以外の言語ユーザーは、タッチキーボードで記号がサポートされていない場合は、最初のセットアップ中に本体に物理キーボードが接続されている必要があります。
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>プライベート CA 証明書をコンソールにインストールする
<a name="Certs"> </a>

Microsoft Teams のルームコンソールは、接続先のサーバーで使用されている証明書を信頼する必要があります。 O365 の場合、これらのサーバーはパブリックの証明機関を使用し、これらは Windows 10 で自動的に信頼されるため、この処理は自動的に行われます。 証明機関が非公開の場合 (Active Directory と Windows 証明機関を使ったオンプレミスの展開など)、次の2つの方法で、Microsoft Teams のルームコンソールに証明書を追加することができます。
  
- コンソールを Active Directory に参加すると、証明機関が Active Directory に公開されている場合は、必要な証明書が自動的に追加されます (通常の展開オプション)。
    
- イメージング処理の後に証明書を手動でインストールすることができます。 この操作を行う前に、[本体の初期設定](console.md#Initial)を完了する必要があります。
    
### <a name="to-manually-install-the-certificate"></a>証明書を手動でインストールするには 

1. CA 証明書をお使いのコンピューターにダウンロードして、C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer に保存します。
    
2. コンソールを管理モードで配置します (「[管理者モードとデバイス管理」を](room-systems-v2-operations.md#AdminMode)参照してください)。
    
3. 次のコマンドを実行します。
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Active Directory ドメインに参加する (オプション)
<a name="Certs"> </a>

Microsoft Teams のルームコンソールをドメインに参加できます。 Microsoft Teams のルームコンソールは、多くのワークステーションポリシーが Microsoft Teams のルームと互換性がないため、PC ワークステーションとは別の OU に配置する必要があります。 一般的な例としては、Microsoft Teams のルームが自動的に起動しないようにするためのパスワード適用ポリシーがあります。 GPO 設定の管理については、「 [Microsoft Teams ルームを管理](room-systems-v2-operations.md)する」を参照してください。
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Microsoft Teams のルームをドメインに参加するには

1. 管理者アカウントから本体にサインインします (「[管理者モードとデバイス管理」を](room-systems-v2-operations.md#AdminMode)参照してください)。
    
2. 管理者特権で Powershell コマンド プロンプトを起動します。
    
3. Powershell に次のコマンドを入力します。
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

たとえば、完全修飾ドメインが redmond.corp.microsoft.com で、Microsoft Teams のルームコンソールを "Resources" OU の子である "Microsoft Teams 室" OU に追加したい場合、コマンドは次のようになります。
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 ドメインに参加するときにコンピューター名を変更するには、-NewName フラグの後にコンピューターの新しい名前を指定します。
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Microsoft Teams のルーム展開のチェックリスト
<a name="Checklist"> </a>

本体とそのすべての周辺機器が完全に設定されていることを確認するために、次のチェックリストを使用します。
  
**アプリケーションの設定**

|||
|:-----|:-----|
|☐  <br/> |ルーム アカウント名と電話番号 (PSTN が有効な場合) が、コンソール画面の右上に正しく表示される  <br/> |
|☐  <br/> |Windows コンピューター名が正しく設定されている (リモート管理に役立つ)  <br/> |
|☐  <br/> |管理者アカウントのパスワードが設定されており、確認済みである  <br/> |
|☐  <br/> |すべてのファームウェア更新プログラムが適用されました  <br/> |
   
**オーディオ/ビデオ周辺機器**

|||
|:-----|:-----|
|☐  <br/> |カメラ周辺機器のファームウェアのバージョンが正しい (該当する場合)  <br/> |
|☐  <br/> |カメラ機能と最適な配置  <br/> |
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

[Microsoft Teams のルームを計画する](skype-room-systems-v2-0.md)
  
[Microsoft Teams ルームの展開](room-systems-v2.md)
  
[Microsoft Teams 室コンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](skype-room-systems-v2.md)
