---
title: 環境を準備する
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Microsoft Teams Rooms を展開するためのインフラストラクチャを準備して、すべての機能を利用できるようにする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4e479a3bc51cdab49a742d9084601505f13020d8
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761249"
---
# <a name="prepare-your-environment"></a>環境を準備する

このセクションでは、Microsoft Teams Rooms の全機能を使用できるように環境を準備するために必要な手順の概要を説明します。
  
1. Microsoft Teams Rooms コンソールごとにリソース アカウントを準備します。 詳細については、「[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)」を参照してください。
    
2. デバイスが使用できるように動作するネットワークまたはインターネット接続があることを確認します。
  
3. エクスペリエンスを向上させるために、Microsoft ではデータを収集します。 Microsoft にデータの収集を許可するには、次のサイトを許可します。

   - テレメトリ クライアント エンドポイント: https://vortex.data.microsoft.com/
   - テレメトリ設定エンドポイント: https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-resource-account"></a>リソース アカウントを作成してテストする

*リソース アカウント* は、Microsoft Teams Rooms クライアントが予定表などのExchangeから機能にアクセスし、Microsoft Teamsに接続するために使用するアカウントです。 詳細については、「[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)」を参照してください。
  
### <a name="check-network-availability"></a>ネットワークの可用性を確認する

適切に機能するには、Microsoft Teams Roomsが次の要件を満たすワイヤード (有線) ネットワークにアクセスできる必要があります。
  
- Active Directory または Azure Active Directory (Azure AD) インスタンス、および Microsoft ExchangeおよびMicrosoft Teamsへのアクセス。

- DHCP を使用して IP アドレスを提供することができるサーバーへのアクセス。 最初のユニットの起動時に、静的 IP アドレスを使用して Microsoft Teams Rooms を構成することはできません。

- HTTP ポート 80 および 443 にアクセスします。

- オンプレミスのSkype for Business Server実装用[のサーバーのポートとプロトコルの要件](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)、または[Microsoft Teamsの URL と IP アドレス範囲のMicrosoft 365とOffice 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)に関するページで説明されているように構成された TCP ポートと UDP ポート。

プロキシを介してネットワークが動作している場合は、プロキシのアドレスまたはスクリプトの情報も必要です。
    
> [!IMPORTANT]
> Microsoft Teams Rooms は、会議室の通常の操作を妨害する可能性があるため、プロキシ認証をサポートしていません。 運用環境に移行する前に、Microsoft Teams Rooms がプロキシ認証から除外されていることを確認してください。

> [!IMPORTANT]
> 有線の 1 Gbps ネットワーク接続を使用して、必要な帯域幅を確保してください。

> [!NOTE]
> Microsoft Teams Rooms のソフトウェア更新プログラムは、ビジネス向け Microsoft Store から自動的にダウンロードされます。 会議室コンソールがストアにアクセスして自己更新できるかどうかを確認するには、「[ビジネスおよび教育機関向け Microsoft Store の前提条件](/microsoft-store/prerequisites-microsoft-store-for-business)」を参照してください。
  
### <a name="certificates"></a>証明書

Microsoft Teams Rooms のデバイスでは、Exchange Web サービス、Microsoft Teams、Skype for Business、ネットワークの使用量および認証に証明書を使用します。 関連サーバーがパブリック証明書を使用している場合 (これは、オンラインおよび一部のオンプレミス展開の場合) は、証明書をインストールするために管理者側でそれ以上の操作は必要ありません。 一方、証明機関がプライベート CA である場合、デバイスはその CA を信頼する必要があります。 つまり、デバイスに CA + CA チェーン証明書がインストールされます。 デバイスをドメインに追加すると、このタスクが自動的に実行される場合があります。
  
他の Windows クライアントの場合と同じ方法で、証明書をインストールします。

> [!IMPORTANT]
> プロキシ サーバーが内部署名された証明書を使用している場合は、ルート CA を含む内部証明書チェーンをMicrosoft Teams Rooms デバイスにインストールする必要があります。
  
> [!NOTE]
> Microsoft Teams Rooms で Skype for Business Server を使用するには、証明書が必要となる場合があります。
  
### <a name="proxy"></a>プロキシ

Microsoft Teams Rooms は、Windows OS からプロキシ設定を継承するように設計されています。 Windows OS には、次の方法でアクセスします。
  
1. Microsoft Teams Rooms UI で、設定ギア アイコンをクリックします。これにより、デバイスのローカルの管理者パスワード (既定のパスワードは「**sfb**」) が求められます。
2. **[設定]** をタップし、**[Windows に移動]** ボタンをタップします。次に、**[管理サインインに移動]** ボタンをタップしてから、**[管理者]** ボタンをクリックします (コンピューターが参加しているドメインである場合は **[その他のユーザー]** を選択してから、ユーザー名として .\admin を使用します)。
3. **[Windows を検索]** ボックスの左下で regedit を入力します (画面を長押しするか、右クリックして **[管理者として実行]** を選択します)。
4. HKEY_USERS フォルダーをクリックして (コンピューター ユーザーの SID の一覧が表示されます)、ルート フォルダー HKEY_USERS が選択されていることを確認してください。
       
5. [ファイル] をクリックし、**[ハイブの読み込み]** を選択します。
6. **C:\Users\Skype** フォルダーに移動し、ファイル名ボックス NTUSER.dat を入力し、開くボタンを押します

7. 新たに読み込まれたハイブのキー名が求められます。「Skype」と入力します (Skype ユーザーのレジストリ設定が表示されます)。
 
8. Skype キーを開き、HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings を参照して、次の設定が入力されていることを確認します。 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    ProxyServer が存在しない場合は、このキーを文字列として追加し、xx.xx.xx.xx:8080 をプロキシ サーバーの IP/ホストとポートに変更する必要があります。
 
    お客様が PAC ファイルを使用している場合、構成は次の例のようになります。

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. 変更を完了したら、Skype ユーザー キー (Skype のルート フォルダー) を強調表示し、レジストリのファイル メニューから [ハイブのアンロード] を選択します (確認が求められるので、[**はい**] を選択します)。
    
10. これで、レジストリ エディターを閉じて、Windows の検索ボックスに logoff と入力できます。
    
11. サインイン画面に戻り、**Skype** ユーザーを選択します。 上記のすべての手順を正常に完了した場合は、Microsoft Teams Rooms デバイスのサインインに成功します。
    
Microsoft Teams Roomsに必要な FQDN、ポート、IP アドレス範囲の詳細については、[ネットワーク セキュリティ](./security.md#network-security)に関する記事を参照してください。
  
### <a name="admin-group-management"></a>管理グループの管理

ドメイン (Azure Active Directoryまたは Active Directory) に参加することを選択した場合は、Microsoft エンドポイント マネージャー、グループ ポリシー、またはローカル コンピューター管理を使用して、ドメイン内のWindows PC の場合と同様に、セキュリティ グループをローカル管理者として設定できます。 そのセキュリティ グループのどのメンバーでも、各自の資格情報を入力して設定をロック解除することができます。
  
> [!NOTE]
> Microsoft Teams Rooms デバイスがドメインとの信頼関係を失った場合 (たとえば、Microsoft Teams Rooms をドメインに参加させた後にドメインから削除した場合)、デバイスを認証して設定を開くことはできません。 回避策では、ローカルの管理者アカウントでログインします。 
  
## <a name="local-accounts"></a>ローカル アカウント

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft Teams Rooms のローカル ユーザー アカウント

Teams Roomsには、"Skype" という名前のパスワードなしのローカル アカウントが含まれています。 このアカウントは、Teams Rooms アプリを起動するためにWindowsにサインインするために使用されます。 このアカウントにパスワードを適用することはサポートされていません。 詳細については、「[Microsoft Teams Rooms セキュリティ](security.md)」を参照してください。
  
### <a name="admin---local-administrator-account"></a>"Admin" - ローカル管理者アカウント

Microsoft Teams Rooms の既定のパスワードは "sfb" に設定されます。 パスワードは、管理 モードまたはAutoUnattend.xml ファイルを使用してローカルで変更できます (ADK の Windows System Image Manager を使用して xml ファイルに変更を加えます)。
  
> [!CAUTION]
> できるだけ早く Microsoft Teams Rooms のパスワードを変更してください。 
  
ローカル管理者パスワードは設定時の選択肢として含まれません。

管理 アカウントの詳細については、[Microsoft Teams Rooms セキュリティ](security.md)に関する記事を参照してください。
  
### <a name="machine-account"></a>コンピューター アカウント

Windowsデバイスと同様に、[コンピューター名の変更について] **設定** \>  \>右クリックすると、**コンピューター名の名前を変更** できます。
  
ドメインに参加した後でコンピューターの名前を変更する場合は、PowerShell コマンドである [Rename-Computer](/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-7.2) を使用し、その後にコンピューターの新しい名前を付けます。
  
## <a name="related-topics"></a>関連項目

[Microsoft Teams Rooms を計画する](rooms-plan.md)

[Microsoft Teams Rooms の要件](requirements.md)
  
[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)
  
[Microsoft Teams Rooms コンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](rooms-manage.md)

[ビジネスおよび教育機関向け Microsoft Store の前提条件](/microsoft-store/prerequisites-microsoft-store-for-business)
