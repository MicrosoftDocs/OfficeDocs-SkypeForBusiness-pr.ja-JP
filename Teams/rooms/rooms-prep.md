---
title: 環境を準備する
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: すべての機能を活用できるように、Microsoft Teams 室を展開するためのインフラストラクチャを準備する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a8252151dcad1c8e483394c6268d445376f25973
ms.sourcegitcommit: 2cc36c954200f50de33b909856b33fe0a9a6b7a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45125960"
---
# <a name="prepare-your-environment"></a>環境を準備する

このセクションでは、Microsoft Teams ミーティングの全機能を使用できるように環境を準備するために必要な手順の概要を説明します。
  
1. Microsoft Teams ミーティングの各コンソールにデバイス アカウントを準備します。 詳細については、「[Microsoft Teams ミーティングをデプロイする](rooms-deploy.md)」を参照してください。
    
2. デバイスが使用できるように動作するネットワークまたはインターネット接続があることを確認します。 
    
   - DHCP を使用して IP アドレスを受信できるようにする必要があります。 (Microsoft Teams ミーティングを最初のユニットの起動時に静的 IP アドレスを使って構成することはできませんが、その後でデバイスの静的 IP アドレスを、デバイス上または上流のスイッチやルーターで構成することができます)。
   - 次のポートが開かれている必要があります (メディアの通常のポートも開かれている必要があります)。
   - HTTPS: 443
   - HTTP:80
   - プロキシを介してネットワークが動作している場合は、プロキシのアドレスまたはスクリプトの情報も必要です。
    
     > [!IMPORTANT]
     > Microsoft Teams room は、会議室の通常の操作に影響を与える可能性があるため、プロキシ認証をサポートしていません。 運用に入る前に、Microsoft Teams の会議室がプロキシ認証から除外されていることを確認します。
  
3. エクスペリエンスを向上させるために、Microsoft ではデータを収集します。 Microsoft にデータの収集を許可するには、次のサイトをホワイトリストに登録します。

   - テレメトリ クライアント エンドポイント: https://vortex.data.microsoft.com/
   - テレメトリ設定エンドポイント: https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>デバイス アカウントを作成してテストする

*デバイス アカウント*は、Microsoft Teams ミーティング クライアントが、予定表などの Exchange の機能にアクセスし、Skype for Business を有効にするために使用するアカウントです。 詳細については、「[Microsoft Teams ミーティングをデプロイする](rooms-deploy.md)」を参照してください。
  
### <a name="check-network-availability"></a>ネットワークの可用性を確認する

適切に機能するために、Microsoft Teams ミーティング デバイスには、以下の要件を満たす有線ネットワークにアクセスする必要があります。
  
- Active Directory または Azure Active Directory (Azure AD) インスタンスと、Microsoft Exchange および Skype for Business Server へのアクセス。
- DHCP を使用して IP アドレスを提供することができるサーバーへのアクセス。 Microsoft Teams のルームは、最初のユニットの起動時に静的 IP アドレスを使って構成することはできません。
- HTTP ポート 80 および 443 にアクセスします。
- オンプレミスの Skype for Business Server の実装の場合は[サーバーのポートとプロトコルの要件](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)、microsoft Teams または Skype for business online の実装では、 [Microsoft 365 および Office 365 の url と IP アドレスの範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)の説明に従って構成された TCP および UDP ポート。

> [!IMPORTANT]
> 有線の 1 Gbps ネットワーク接続を使用して、必要な帯域幅を確保してください。

> [!NOTE]
> Microsoft Teams ミーティングのソフトウェア更新プログラムは、ビジネス向け Microsoft Store から自動的にダウンロードされます。 会議室コンソールがストアにアクセスして自己更新できるかどうかを確認するには、「[ビジネスおよび教育機関向け Microsoft Store の前提条件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)」を参照してください。
  
### <a name="certificates"></a>証明書

Microsoft Teams ミーティングのデバイスでは、Exchange Web サービス、Microsoft Teams、Skype for Business、ネットワークの使用量および認証に証明書を使用します。 関連のあるサーバーがパブリック証明書を使用していて、これがオンラインおよびオンプレミスのデプロイの場合、管理者が証明書をインストールするために必要な操作はありません。 一方、証明機関がプライベート CA (オンプレミスのデプロイでは一般的) の場合、デバイスはこの CA を信頼する必要があります。これは、デバイスに CA と CA チェーン証明書がインストールされていることを意味します。 デバイスをドメインに追加すると、このタスクが自動的に実行される場合があります。
  
他の Windows クライアントの場合と同じ方法で、証明書をインストールします。 
  
> [!NOTE]
> Microsoft Teams ミーティングで Skype for Business Server を使用するには、証明書が必要となる場合があります。
  
### <a name="proxy"></a>プロキシ

Microsoft Teams ミーティングは、Windows OS からプロキシ設定を継承するように設計されています。 Windows OS には、次の方法でアクセスします。
  
1. Microsoft Teams ミーティング UI で、設定ギア アイコンをクリックします。これにより、デバイスのローカルの管理者パスワード (既定のパスワードは「**sfb**」) が求められます。
2. **[設定]** をタップし、**[Windows に移動]** ボタンをタップします。次に、**[管理サインインに移動]** ボタンをタップしてから、**[管理者]** ボタンをクリックします (コンピューターが参加しているドメインである場合は **[その他のユーザー]** を選択してから、ユーザー名として .\admin を使用します)。
3. **[Windows を検索]** ボックスの左下で regedit を入力します (画面を長押しするか、右クリックして **[管理者として実行]** を選択します)。
4. HKEY_USERS フォルダーをクリックして (コンピューター ユーザーの SID の一覧が表示されます)、ルート フォルダー HKEY_USERS が選択されていることを確認してください。
       
5. [ファイル] をクリックし、**[ハイブの読み込み]** を選択します。
6. **C:\Users\Skype**フォルダーを参照して、[ファイル名] ボックスに「NTUSER.dat」と入力し、[開く] ボタンを押します。

7. 新たに読み込まれたハイブのキー名が求められます。「Skype」と入力します (Skype ユーザーのレジストリ設定が表示されます)。
 
8. Skype キーを開き、HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings を参照して、次の設定が入力されていることを確認します。 
    
    `[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]`
    
    `"MigrateProxy"=dword:00000001`
    
    `"ProxyEnable"=dword:00000001`
    
    `"ProxyServer"="xx.xx.xx.xx:8080"`
    
    ProxyServer が存在しない場合は、このキーを文字列として追加し、xx.xx.xx.xx:8080 をプロキシ サーバーの IP/ホストとポートに変更する必要があります。
    
9. 変更を完了したら、Skype ユーザー キー (Skype のルート フォルダー) を強調表示し、レジストリのファイル メニューから [ハイブのアンロード] を選択します (確認が求められるので、**[はい]** を選択します)。
    
10. これで、レジストリ エディターを閉じて、Windows の検索ボックスに logoff と入力できます。
    
11. サインイン画面に戻り、**Skype** ユーザーを選択します。 上記のすべての手順を正常に完了した場合は、Microsoft Teams ミーティング デバイスのサインインに成功します。
    
To use this application, you must be able to connect to the endpoints described below. To see the IP addresses, expand the IP address section below the table describing the traffic flow.
  
**ファイアウォール プロキシのホスト名またはポートの例**

|用途|ソースまたは資格情報|送信元ポート|接続先|CDN|Office 365 向け ExpressRoute|接続先 IP|送信先ポート|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|認証と ID  <br/> |「 [Microsoft 365 と Office 365 の認証と id](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) 」を参照してください。 <br/> |||
|ポータルと共有  <br/> |「 [Microsoft 365 管理センターと共有」を参照し](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity)てください。 <br/> |||
|SIP 信号  <br/> |クライアント コンピューターまたはログオンしているユーザー  <br/> |エフェメラル ポート  <br/> |\*.contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype for Business の IP 範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|永続共有オブジェクト モデル (PSOM) 接続による Web 会議  <br/> |クライアント コンピューターまたはログオンしているユーザー  <br/> |エフェメラル ポート  <br/> |\*.contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype for Business の IP 範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|HTTPS ダウンロード  <br/> |クライアント コンピューターまたはログオンしているユーザー  <br/> |エフェメラル ポート  <br/> |\*.contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype for Business の IP 範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|オーディオ  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |TCP/UDP 50,000-50019  <br/> |\*.contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype for Business の IP 範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443、UDP 3478、TCP/UDP 50,000-59,999  <br/> |
|ビデオ  <br/> |クライアント コンピューターまたはログオンしているユーザー  <br/> |TCP/UDP 50,020 ～ 50,039  <br/> |\*.contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype for Business の IP 範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443、UDP 3478、TCP/UDP 50,000-59,999  <br/> |
|デスクトップの共有  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |TCP/UDP 50,040 ～ 50,059  <br/> |\*.contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype for Business の IP 範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443、50,000-59,999  <br/> |
|Lync Mobile push notifications for Lync Mobile 2010 on iOS devices. You don't need this for Android, Nokia Symbian or Windows Phone mobile devices.  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |エフェメラル ポート  <br/> |\*.contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype for Business の IP 範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Skype テレメトリ  <br/> |クライアント コンピューターまたはログオンしているユーザー  <br/> |エフェメラル ポート  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |なし  <br/> |いいえ  <br/> |該当なし  <br/> |TCP 443  <br/> |
|Skype クライアントの簡単なヒント  <br/> |クライアント コンピューターまたはログオンしているユーザー  <br/> |エフェメラル ポート  <br/> |quicktips.skypeforbusiness.com  <br/> |×  <br/> |いいえ  <br/> |該当なし  <br/> |TCP 443  <br/> |

> [!NOTE]
> Contoso.com と broadcast.skype.com のワイルドカードは、Microsoft 365 または Office 365 専用に使用されるノードの長いリストを表します。 
  
### <a name="create-provisioning-packages"></a>プロビジョニング パッケージを作成する

プロビジョニングパッケージを使用して、Exchange Server、Microsoft 365、または Office 365 への認証を行います。
  
### <a name="admin-group-management"></a>管理グループの管理

ドメインの参加後、ドメイン内の Widonws PC の場合と同じ方法で、グループ ポリシーまたはローカルのコンピュータの管理を使用して、ローカル管理者としてセキュリティ グループを設定できます。 そのセキュリティ グループのどのメンバーでも、各自の資格情報を入力して設定をロック解除することができます。
  
> [!NOTE]
> Microsoft Teams Rooms デバイスがドメインとの信頼関係を失った場合 (たとえば、Microsoft Teams Rooms をドメインに参加させた後にドメインから削除した場合)、デバイスを認証して設定を開くことはできません。 回避策では、ローカルの管理者アカウントでログインします。 
  
## <a name="local-accounts"></a>ローカル アカウント

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft Teams ミーティングのローカル ユーザー アカウント

通常、デバイス アカウントではパスワードを使用しません。 パスワードを指定することは可能ですが、パスワードが期限切れとなった場合にユーザーがコンソール アプリケーションケーションからロックアウトされる可能性などの因果関係があります。 その結果として、管理者は、パスワードが期限切れにならないようにする必要があります。
  
### <a name="admin---local-administrator-account"></a>"Admin" - ローカル管理者アカウント

Microsoft Teams ミーティングの既定のパスワードは "sfb" に設定されます。 パスワードは、[Windows の設定] \>[Windows に移動] の順に移動してローカルで変更するか、AutoUnattend.xml ファイルで変更することができます (ADK からの Windows システム イメージ マネージャーを使用して xml ファイルを変更します)。
  
> [!CAUTION]
> できるだけ早く Microsoft Teams ミーティングのパスワードを変更してください。 
  
ドメイン管理者をローカル管理者として設定したグループ ポリシーを設定することで、ローカル管理者のパスワードを管理することもできます。
  
ローカル管理者パスワードは設定時の選択肢として含まれません。
  
### <a name="machine-account"></a>コンピューター アカウント

その他の Windows デバイスと同様に、[設定] \> [バージョン情報] \> [PC 名の変更] の順に右クリックして、コンピューターの名前を変更することができます。
  
 ドメインへの参加後にコンピューターの名前を変更する場合は、Rename-Computer PowerShell コマンドを使用し、その後にコンピューターの新しい名前を続けます。
  
## <a name="related-topics"></a>関連項目

[Microsoft Teams ミーティングを計画する](rooms-plan.md)

[Microsoft Teams ミーティングの要件](requirements.md)
  
[Microsoft Teams ミーティングをデプロイする](rooms-deploy.md)
  
[Microsoft Teams ミーティング コンソールを構成する](console.md)
  
[Microsoft Teams ミーティングの管理](rooms-manage.md)

[ビジネスおよび教育機関向け Microsoft Store の前提条件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 
