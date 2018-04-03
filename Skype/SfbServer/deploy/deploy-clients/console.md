---
title: Skype Room Systems バージョン 2 コンソールを構成する
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: この記事では、Skype Room Systems バージョン 2 コンソール デバイスとその周辺機器の設定方法を説明します。
ms.openlocfilehash: 6e2ec8384387cefd074342abb3da316288af1f0f
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2018
---
# <a name="configure-a-skype-room-systems-v2-console"></a>Skype Room Systems バージョン 2 コンソールを構成する
 
この記事では、Skype Room Systems バージョン 2 コンソール デバイスとその周辺機器の設定方法を説明します。
  
ビジネスおよび Exchange アカウントに必要な Skype が既に作成して[Skype ルーム システムの配置のバージョン 2](room-systems-v2.md)で説明したようにテストする場合のみ、この手順を実行する必要があります。 ハードウェアとソフトウェアの[Skype ルーム システム v2 の要件](../../plan-your-deployment/clients-and-devices/requirements.md)」に記載する必要があります。 このトピックには次のセクションが含まれています。
  
- [インストール イメージを準備する](console.md#Prep_Image)
    
- [タブレット デバイスにプライベート CA 証明書をインストールします。](console.md#Certs)
    
- [Windows 10 と Skype ルーム システム v2 のコンソール アプリケーションをインストールします。](console.md#Reimage)
   
- [コンソールの初期設定](console.md#Initial)
    
- [Skype ルーム システム v2 の展開のチェックリスト](console.md#Checklist)
    
> [!NOTE]
> Skype ルーム システム v2 は、ビジネス環境をデバイスのアカウントが正しく設定されて[Skype ルーム システムの配置のバージョン 2](room-systems-v2.md)で説明したように正しく構成されている Skype でのみ動作します。 
  
## <a name="prepare-the-installation-image"></a>インストール イメージを準備する
<a name="Prep_Image"> </a>

Surface Pro 4 または Surface Pro の Skype ルーム システム v2 のアプリケーションをインストールするには、FAT32 ディスクとしてフォーマットされたメモリの 32 GB 以上の USB ストレージ デバイスが必要です。 存在しないはずの他のデバイス上のファイルは、USB 記憶装置上の既存のファイルはすべて失われます。 
  
> [!NOTE]
> 次の手順に従ってコンソール イメージを作成しないと、予期しない動作が発生する可能性があります。 Skype ルーム システム v2 のイメージの作成については、Windows 10 企業記念日の更新プログラム (バージョン 1607) がサポートされていません。 
  
> [!NOTE]
> Windows 10 企業記念日を更新、Windows ストアを使用して Skype ルーム システム v2 更新 3 への移動で既存の Skype ルーム システム v2 機能しますが、次のように、新規インストールを行う必要があります。 
  
1. [MSU](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu)をダウンロードします。
2. [CreateSrsMedia.ps1 スクリプト](https://go.microsoft.com/fwlink/?linkid=867842)をダウンロードします。
3. MSU を KB4056892 の CreateSrsMedia.ps1 スクリプトと同じディレクトリに配置します。
4. 10 の Windows コンピューターで管理者特権のプロンプトから CreateSrsMedia.ps1 スクリプトを実行します。


Skype ルーム システム v2 の USB セットアップ ディスクを作成するスクリプトの指示に従います。 完了したら、USB ディスクをコンピューターから削除し、 [Windows の 10 をインストール](console.md#Reimage)して Skype ルーム システム v2 のコンソール アプリケーションです。
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a>Windows 10 と Skype Room Systems バージョン 2 コンソール アプリをインストールする 
<a name="Reimage"> </a>

次に、作成したイメージを適用する必要があります。 タブレットは、アプライアンスとして実行され、Skype ルーム システム v2 アプリケーションのみを実行するのには既定のユーザーを指定します。 
  
1. タブレットを電源に接続します。 完全に電源オフの状態から開始します。 必要に応じて、タブレットの電源が切れるまで、電源ボタンを押したままにします。
    
2. USB セットアップ ディスクをタブレットに取り付けます。
    
3. タブレットのボリューム ダウン (-) ボタンを押したままにします。 
    
4. タブレットの電源ボタンを押して、離します。
    
5. Windows セットアップが起動したら、ボリューム ダウン (-) ボタンを離します。
    
6. インストールが完了したら、システムがシャット ダウンします。
    
システムがシャット ダウンした後、USB のセットアップ ディスクを削除すると安全です。 この段階で、タブレットをドックに設置し、お使いの会議室に必要な周辺機器を接続できます。 製造元の指示を参照してください。
  
 
### <a name="selecting-a-language-in-creators-update"></a>Creators Update での言語の選択

作成者の更新では、暗黙の言語の選択が必要な実際のアプリケーションの言語を使用してユーザーを提供しないシナリオで ApplyCurrentRegionAndLanguage.ps1 スクリプトを使用する必要があります (など、フランス語で発生するようにアプリケーションが欲しいが、次の英語で)。
  
> [!NOTE]
> 次の操作指示は、Windows Creators Update を使用して作成されたデバイスに対してのみ機能します。 新しいプロビジョニング システムに対して適切に再イメージングされていないレガシー/販売中のシステムは、これらの操作指示を利用できませんが、手動での介入を必要とする最初の問題からは損害を受けます (Anniversary Edition では、セットアップの一部としてアプリの言語を明示的に選ぶことができます)。 
  
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
    
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    
13. システムを再起動します。
    
Skype ルーム システムのバージョン 2 のデバイスに、目的の言語が適用されます。
## <a name="initial-set-up-of-the-console"></a>コンソールの初期設定 
<a name="Initial"> </a>

Windows をインストールすると、Skype ルーム システム v2 アプリケーションが次回起動したとき、または、/reboot オプションが選択された場合の初期のセットアップ プロセスに移動します。
  
1. [ユーザー アカウント] 画面が表示されます。デバイスで使用するルーム アカウントの Skype サインイン アドレス (ユーザー@ドメイン形式) を入力します。
    
2. ルーム アカウントのパスワードを入力し、確認のためにもう一度入力します。
    
3. "ドメインの構成] の下で、Skype のビジネス サーバーの FQDN を設定します。 ビジネスの SIP ドメインの Skype ユーザーの Exchange ドメインと異なる場合は、このフィールドに、Exchange ドメインを入力します。
    
4. [ **次へ**] をクリックします。
    
5. [機能] 画面で指定されたデバイスを選択し、[**次へ**] をクリックします。 既定では、自動画面共有はオンで、会議名の非表示はオフになっています。 選択対象のデバイスは次のとおりです。
    
   - 会議用のマイク: 会議室で使用する既定のマイク。
    
   - 会議用のスピーカー: 会議で使用する既定のスピーカー。 
    
   - 既定のスピーカー: HDMI インジェストからのオーディオ用に使用されるスピーカー。
    
    それぞれの項目に、選択できるドロップダウン メニューのオプションがあります。各デバイスについて選択を行う必要があります。
    
6. **[完了]** をクリックします。
    
アプリケーションはビジネス サーバー 2015 の上で入力した資格情報を持つ Skype にサインインします。 すぐに開始する必要がありでこれらの同じ資格情報を使用して Exchange の予定表の同期を開始する必要がありますも。 アプリケーションの使用方法の詳細については、 [Skype ルーム システム バージョン 2 のヘルプ](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)を参照してください。
  
> [!IMPORTANT]
> Skype ルーム システム v2 では、認定されたコンソールのハードウェア (logitech (ロジクール) SmartDock) の存在に依存しています。 Surface Pro 4 または Surface Pro に読み込まれている Skype ルーム システム v2 のアプリケーションが含まれている正常に作成されたイメージはコンソールのハードウェアが検出された場合を除き、過去の初期セットアップ手順は起動しません。 
  
> [!NOTE]
> 英語以外の一部の言語のユーザーは、記号がタッチ キーボードでサポートされない場合に、コンソールに接続した物理的なキーボードが初期設定において必要になることがあります。 
  
### <a name="install-a-private-ca-certificate-on-the-tablet-device"></a>タブレット デバイスにプライベート CA 証明書をインストールする
<a name="Certs"> </a>

Skype ルーム システムのバージョン 2 のデバイスは、ビジネスおよび Exchange のサーバーに接続するため、Skype で使用する証明書を信頼する必要があります。 O365 の場合、これらのサーバーはパブリックの証明機関を使用し、これらは Windows 10 で自動的に信頼されるため、この処理は自動的に行われます。 証明機関がプライベートの場合は Active Directory および Windows の証明機関と設置型展開の 2 とおりの方法で Skype ルーム システム v2 デバイスに証明書を追加できます。
  
- 証明機関が Active Directory に対して公開されていることを前提とした場合 (通常の展開オプション)、デバイスを Active Directory に参加させると、必要な証明書は自動的に追加されます。
    
- イメージング処理の後に証明書を手動でインストールすることができます。この操作を行う前に、[コンソールの初期設定](console.md#Initial)を完了する必要があります。 
    
### <a name="to-manually-install-the-certificate"></a>証明書を手動でインストールするには 

1. CA 証明書をお使いのコンピューターにダウンロードして、C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer に保存します。
    
2. 管理者モードでサーフェスの 4 を配置する ([管理者モードとデバイスの管理](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)を参照してください)。
    
3. 次のコマンドを実行します。
    
  ```
  certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
  ```

### <a name="join-an-active-directory-domain-optional"></a>Active Directory のドメインに参加します (オプション)
<a name="Certs"> </a>

Skype ルーム システム v2 のデバイスは、ドメインに参加できます。 Skype ルーム システム v2 のデバイスは、多くのワークステーションのポリシーは Skype ルーム システム v2 と互換性がないため PC ワークステーションから別の OU に配置してください。 一般的な例は、パスワードの強制ポリシー Skype ルーム システム v2 が自動的に起動できなくなります。 GPO の設定の管理方法については、 [Skype ルームの管理のシステムのバージョン 2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)を参照してください。 
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a>Skype Room System バージョン 2 をドメインに参加させるには

1. では、管理コンソールに記号 ([管理者モードとデバイスの管理](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)を参照してください) を考慮します。
    
2. 管理者特権で Powershell コマンド プロンプトを起動します。
    
3. Powershell に次のコマンドを入力します。
    
  ```
  Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
  ```

たとえば、完全修飾ドメイン redmond.corp.microsoft.com は、「Skype ルーム システム v2」で、Skype ルーム システム v2 のデバイスが必要な場合は、リソース OU の子 OU の場合は、コマンドになります。
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 ドメインに参加させるときに、コンピューターの名前を変更したい場合は、コンピューターの新しい名前の後に、新しい名前のフラグを使用します。
  
## <a name="skype-room-systems-v2-deployment-checklist"></a>Skype Room System バージョン 2 の展開チェックリスト
<a name="Checklist"> </a>

コンソール デバイスとそのすべての周辺機器が完全に構成されていることを最終確認するときは、以下のチェックリストを使用します。
  
**アプリケーションの設定**

|||
|:-----|:-----|
|☐  <br/> |ルーム アカウント名と電話番号 (PSTN が有効な場合) が、コンソール画面の右上に正しく表示される  <br/> |
|☐  <br/> |Windows コンピューター名が正しく設定されている (リモート管理に役立つ)  <br/> |
|☐  <br/> |管理者アカウントのパスワードが設定されており、確認済みである  <br/> |
|☐  <br/> |Surface Pro 4 または Surface Pro のすべてのシステム アップデートが適用済みである  <br/> |
   
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
   
**ドッキング ステーション**

|||
|:-----|:-----|
|☐  <br/> |ケーブルが保護されており、圧迫されていない  <br/> |
|☐  <br/> |HDMI を介したオーディオ インジェストが機能している  <br/> |
|☐  <br/> |HDMI を介したビデオ インジェストが機能している  <br/> |
|☐  <br/> |ドックは自由に回転することができる  <br/> |
|☐  <br/> |表示の明るさが環境に適している  <br/> |
   
## <a name="see-also"></a>この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。
<a name="Checklist"> </a>

#### 

[Skype ルームの計画システム v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Skype の部屋を配置するシステム v2](room-systems-v2.md)
  
[Skype ルーム システム v2 のコンソールを構成します。](console.md)
  
[Skype ルームの管理システム v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

