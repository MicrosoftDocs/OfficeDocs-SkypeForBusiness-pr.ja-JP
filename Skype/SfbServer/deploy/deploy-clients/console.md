---
title: Skype Room Systems バージョン 2 コンソールを構成する
ms.author: jambirk
author: jambirk
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: この資料では、Skype ルーム システム v2 のコンソールとその周辺機器を設定する方法について説明します。
ms.openlocfilehash: 00203c8aa781c489d8a1cc8c2bf91a364bea057f
ms.sourcegitcommit: c7c8e5f6d8b25e68bf071745517d38eb45c1e172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2019
ms.locfileid: "28694721"
---
# <a name="configure-a-skype-room-systems-v2-console"></a>Skype Room Systems バージョン 2 コンソールを構成する
 
この資料では、Skype ルーム システム v2 のコンソールとその周辺機器を設定する方法について説明します。
  
ビジネスおよび Exchange アカウントに必要な Skype が既に作成して[Skype ルーム システムの配置のバージョン 2](room-systems-v2.md)で説明したようにテストする場合のみ、この手順を実行する必要があります。 ハードウェアとソフトウェアの[Skype ルーム システム v2 の要件](../../plan-your-deployment/clients-and-devices/requirements.md)」に記載する必要があります。 このトピックには次のセクションが含まれます。
  
- [インストール メディアを準備します。](console.md#Prep_Media)
    
- [コンソールにプライベート CA 証明書をインストールします。](console.md#Certs)
    
- [Windows 10 と Skype Room Systems バージョン 2 コンソール アプリをインストールする](console.md#Reimage)
   
- [コンソールの初期設定](console.md#Initial)
    
- [Skype ルーム システム v2 の展開のチェックリスト](console.md#Checklist)
    
> [!NOTE]
> Skype ルーム システム v2 は、ビジネス環境をデバイスのアカウントが正しく設定されて[Skype ルーム システムの配置のバージョン 2](room-systems-v2.md)で説明したように正しく構成されている Skype でのみ動作します。
  
## <a name="prepare-the-installation-media"></a>インストール メディアを準備します。
<a name="Prep_Media"> </a>

Skype ルーム システム v2 のコンソール アプリケーションをインストールするには、32 GB 以上の容量を持つ USB ストレージ デバイスが必要です。 存在しないはずのデバイス上のファイルUSB 記憶装置上の既存のファイルはすべて失われます。
  
> [!NOTE]
> 予期しない動作になる可能性があります、次の手順に従って、Skype ルーム システム v2 のインストール メディアを作成するに失敗しました。

> [!NOTE]
> 以下の手順は、新しい Skype ルーム システム v2 のデバイスのイメージにインストール メディアを作成するためです。 既存のデバイスでは、既定では、自動的に更新 Windows を更新し、Windows ストアから。
  
1. [CreateSrsMedia.ps1 スクリプト](https://go.microsoft.com/fwlink/?linkid=867842)をダウンロードします。 
2. Windows 10 マシン上で管理者特権でのプロンプトから CreateSrsMedia.ps1 スクリプトを実行します。
3. Skype ルーム システム v2 の USB セットアップ ディスクを作成するスクリプトの指示に従います。

> [!CAUTION]
> メディアからの作成スクリプトを実行するフォルダーの名前にスペースを含めることはできません。 フォルダー名にスペースがある場合、スクリプトは失敗します。

CreateSrsMedia.ps1 スクリプトは、次のタスクを自動化します。

1. Skype ルーム システム v2 の最新の MSI インストーラーをダウンロードします。
2. ユーザーを指定する必要があります Windows のビルドを決定します。 最も最近リリースされたバージョン可能性がありますまたは可能性がありますいないにテストして Skype ルーム システム v2 のデバイスでの使用をサポートしました。
3. サポートするために必要なコンポーネントをダウンロードします。
4. インストール メディアに必要なコンポーネントをアセンブルします。

完了したら、USB ディスクをコンピューターから削除し、 [Windows の 10 をインストール](console.md#Reimage)して Skype ルーム システム v2 のコンソール アプリケーションです。

    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a>Windows 10 と Skype Room Systems バージョン 2 コンソール アプリをインストールする
<a name="Reimage"> </a>

作成したセットアップ メディアを適用する必要があります。 アプライアンスとターゲット ・ デバイスが実行され、既定のユーザーは、Skype ルーム システム v2 のコンソール アプリケーションを実行するだけに設定されます。

1. ドッキング ステーション (例えば、Surface Pro) でターゲット ・ デバイスをインストールする場合は、ドッキング ステーションから取り外します。

2. ターゲット ・ デバイスがネットワークに接続されていないことを確認します。

3. ターゲット ・ デバイスが AC 電源に接続されていることを確認します。

4. USB セットアップ ディスクをターゲット ・ デバイスに差し込みます。

5. USB セットアップ ディスクから起動します。 製造元の指示を参照してください。 場合は、ターゲット ・ デバイスは、Surface Pro は、USB のセットアップ ディスクから起動するのには次の手順を使用します。

    a. キーを押し、ボリューム ダウン (-) ボタンを押したままです。

    b. キーを押し、電源ボタンを離します。

    c. Windows セットアップが起動したら、ボリューム ダウン (-) ボタンを離します。

8. インストールが完了したら、システムがシャット ダウンします。
    
システムがシャット ダウンした後、USB のセットアップ ディスクを削除すると安全です。 この時点で、(ドッキング ベースの製品を使用する) 場合は、そのドッキング ステーションにターゲット ・ デバイスを配置、会議室に必要な周辺機器を接続してネットワークに接続できます。 製造元の指示を参照してください。
  
### <a name="selecting-a-language"></a>言語を選択します。 

作成者の更新では、暗黙の言語の選択が必要な実際のアプリケーションの言語を使用してユーザーを提供しないシナリオで ApplyCurrentRegionAndLanguage.ps1 スクリプトを使用する必要があります (フランス語、考案するコンソール アプリケーションをするなどが、それは、次の英語で)。
  
> [!NOTE]
> 次の手順は、作成者の Windows 更新プログラムを使用して作成されたコンソールに対してのみ機能します。 新しいプロビジョニング システムでメディアを使用して設定されていないレガシ/市場でのシステムは、これらの手順を使用することはできませんが、この手動による介入を必要とする最初の問題からは低くもする必要があります (記念日のエディションを選択できます、アプリケーションの言語設定の一部として明示的に)。
  
### <a name="to-apply-your-desired-language"></a>必要な言語を適用するには

1. 管理モードに切り替えます。
    
2. [スタート] メニューを選択します。
    
3. ギア アイコンを選択して [**設定**] アプリを起動します。
    
4. 選択**時間&amp;言語**です。
    
5. 選択**地域&amp;言語**です。
    
6. [**言語の追加**] を選択します。
    
7. 追加する言語を選択します。
    
8. [言語] ボックスの一覧に追加した言語を選択します。
    
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
    
Skype ルーム システム v2 のコンソールに、目的の言語が適用されます。
## <a name="initial-set-up-of-the-console"></a>コンソールの初期設定
<a name="Initial"> </a>

Windows をインストールすると、Skype ルーム システム v2 のコンソール アプリケーションが次回起動したとき、または、/reboot オプションが選択された場合の初期のセットアップ プロセスに移動します。
  
1. [ユーザー アカウント] 画面が表示されます。 Skype サインインのアドレスを入力 (user@domain 形式) で、コンソールで使用する部屋のアカウントです。
    
2. ルーム アカウントのパスワードを入力し、確認のためにもう一度入力します。
    
3. "ドメインの構成] の下で、Skype のビジネス サーバーの FQDN を設定します。 ビジネスの SIP ドメインの Skype ユーザーの Exchange ドメインと異なる場合は、このフィールドに、Exchange ドメインを入力します。
    
4. [ **次へ**] をクリックします。
    
5. [機能] 画面で指定されたデバイスを選択し、[**次へ**] をクリックします。 既定では、自動画面共有はオンで、会議名の非表示はオフになっています。 選択対象のデバイスは次のとおりです。
    
   - 会議用のマイク: 会議室で使用する既定のマイク。
    
   - 会議用のスピーカー: 会議で使用する既定のスピーカー。 
    
   - 既定のスピーカー: HDMI インジェストからのオーディオ用に使用されるスピーカー。
    
     それぞれの項目に、選択できるドロップダウン メニューのオプションがあります。各デバイスについて選択を行う必要があります。
    
6. **[完了]** をクリックします。
    
Skype ルーム システム v2 のコンソール アプリケーションは、ビジネス サーバー、上で入力した資格情報を持つ Skype にサインインします。 すぐに開始する必要がありで同じ資格情報を使用して Exchange の予定表の同期を開始する必要がありますも。 コンソール アプリケーションの使用方法の詳細については、 [Skype ルーム システム バージョン 2 のヘルプ](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)を参照してください。
  
> [!IMPORTANT]
> Skype ルーム システム v2 では、認定されたコンソールのハードウェアの存在に依存しています。 Skype ルーム システム v2 のコンソール アプリケーションが含まれている正常に作成されたイメージはコンソールのハードウェアが検出された場合を除き、過去の最初のセットアップ手順は起動しません。 Surface Pro ベースのソリューションでは、Surface Pro が必要に接続するこのチェックに合格するのには、付属のドッキング ハードウェア。
  
> [!NOTE]
> 英語以外の言語の一部のユーザーは、タッチ キーボードでは、シンボルはサポートされていない、初期セットアップ時にコンソールに接続されている物理的なキーボードを必要があります。
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>コンソールにプライベート CA 証明書をインストールします。
<a name="Certs"> </a>

Skype ルーム システム v2 のコンソールでは、ビジネスおよび Exchange のサーバーに接続するため、Skype で使用する証明書を信頼する必要があります。 O365 の場合、これらのサーバーはパブリックの証明機関を使用し、これらは Windows 10 で自動的に信頼されるため、この処理は自動的に行われます。 証明機関がプライベートの場合は Active Directory および Windows の証明機関と設置型展開の 2 とおりの方法で Skype ルーム システム v2 のコンソールに証明書を追加できます。
  
- コンソールを Active Directory に参加させることができ、証明機関を指定する必要な証明書が Active Directory (通常の展開オプション) を発行するが自動的に追加します。
    
- イメージング処理の後に証明書を手動でインストールすることができます。 これを行う前に[初期がコンソールの設定](console.md#Initial)を完了する必要があります。
    
### <a name="to-manually-install-the-certificate"></a>証明書を手動でインストールするには 

1. CA 証明書をお使いのコンピューターにダウンロードして、C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer に保存します。
    
2. 管理者モードでコンソールを配置する ([管理者モードとデバイスの管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)を参照してください)。
    
3. 次のコマンドを実行します。
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>(省略可能) Active Directory のドメインに参加します。
<a name="Certs"> </a>

Skype ルーム システム v2 のコンソールは、ドメインに参加できます。 Skype ルーム システム v2 のコンソールは、多くのワークステーションのポリシーは Skype ルーム システム v2 と互換性がないため PC ワークステーションから別の OU に配置してください。 一般的な例は、パスワードの強制ポリシー Skype ルーム システム v2 が自動的に起動できなくなります。 GPO 設定の管理の詳細については、「[Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md)」を参照してください。
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a>Skype Room System バージョン 2 をドメインに参加させるには

1. では、管理コンソールに記号 ([管理者モードとデバイスの管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)を参照してください) を考慮します。
    
2. 管理者特権で Powershell コマンド プロンプトを起動します。
    
3. Powershell に次のコマンドを入力します。
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

たとえば、完全修飾ドメイン redmond.corp.microsoft.com は、「Skype ルーム システム v2」で、Skype ルーム システム v2 のコンソールが必要な場合は、リソース OU の子 OU の場合は、コマンドになります。
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 ドメインに参加させるときに、コンピューターの名前を変更したい場合は、コンピューターの新しい名前の後に、新しい名前のフラグを使用します。
  
## <a name="skype-room-systems-v2-deployment-checklist"></a>Skype ルーム システム v2 の展開のチェックリスト
<a name="Checklist"> </a>

コンソールとそのすべての周辺機器が完全に構成されている最終的な検証を行う際に、次のチェックリストを使用します。
  
**アプリケーションの設定**

|||
|:-----|:-----|
|☐  <br/> |ルーム アカウント名と電話番号 (PSTN が有効な場合) が、コンソール画面の右上に正しく表示される  <br/> |
|☐  <br/> |Windows コンピューター名が正しく設定されている (リモート管理に役立つ)  <br/> |
|☐  <br/> |管理者アカウントのパスワードが設定されており、確認済みである  <br/> |
|☐  <br/> |すべてのファームウェア更新プログラムが適用されています。  <br/> |
   
**オーディオ/ビデオ周辺機器**

|||
|:-----|:-----|
|☐  <br/> |カメラ周辺機器のファームウェアのバージョンが正しい (該当する場合)  <br/> |
|☐  <br/> |カメラの機能と、最適な位置を指定しました。  <br/> |
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
   
## <a name="see-also"></a>この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。
<a name="Checklist"> </a>

[Plan for Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Skype Room System バージョン 2 を展開する](room-systems-v2.md)
  
[Skype Room Systems バージョン 2 コンソールを構成する](console.md)
  
[Skype Room Systems バージョン 2 を管理する](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)