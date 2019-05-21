---
title: 環境の準備
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection: M365-voice
description: この記事では、Microsoft Teams のルームを展開するためのインフラストラクチャの準備について説明します。
ms.openlocfilehash: 99f1ab71e2bf65e0d6fde0287a82942569c68169
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288542"
---
# <a name="prepare-your-environment"></a>環境を準備する

このセクションには、Microsoft Teams のルームのすべての機能を使用できるように、環境の準備に必要な手順の概要が記載されています。
  
1. Microsoft Teams の各ルームコンソールのデバイスアカウントを準備します。 詳しくは、「 [Microsoft Teams ルームの展開](room-systems-v2.md)」をご覧ください。
    
2. デバイスが使用する、正常に動作しているネットワーク/インターネット接続があることを確認します。 
    
   - DHCP を使って IP アドレスを受信できる必要があります。 (Microsoft Teams ルームは、最初のユニットの起動時に静的 IP アドレスを使って構成することはできませんが、その後でデバイスの静的 IP をデバイスまたは上流のスイッチまたはルータで構成できます)。
    
   - 次のポートを開いておく必要があります (メディアの通常のポートを開くことに加えて)。
    
   - HTTPS: 443
    
   - HTTP: 80
    
   - プロキシを介してネットワークが動作している場合は、プロキシのアドレスまたはスクリプトの情報も必要です。
    
     > [!NOTE]
     > Microsoft Teams Rooms は、HDMI インジェストの機能 (ビデオ、オーディオ) に関する問題を引き起こすことが確認されている、HDCP 入力をサポートしていません。 Microsoft Teams Rooms に接続されたスイッチの HDCP オプションがオフになっていることを必ず確認してください。 
  
3. エクスペリエンスを改善するために、マイクロソフトではデータを収集しています。 データを収集するために、以下のサイトをホワイトリストに記載しておく必要があります。
    
   - テレメトリクライアントエンドポイント:https://vortex.data.microsoft.com/
    
   - テレメトリ設定エンドポイント:https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>デバイス アカウントを作成してテストする

*デバイスアカウント*は、Microsoft Teams の会議室クライアントが Exchange の機能にアクセスするために使用するアカウントであり、予定表など、Skype for business を有効にします。 詳しくは、「 [Microsoft Teams ルームの展開](room-systems-v2.md)」をご覧ください。
  
### <a name="check-network-availability"></a>ネットワークの状態をチェックする

Microsoft Teams の会議室デバイスは、適切に機能するために、以下の要件を満たす有線ネットワークへのアクセス権を持っている必要があります。
  
- Active Directory または Azure Active Directory (Azure AD) インスタンスと、Microsoft Exchange および Skype for Business Server へのアクセス。
- DHCP を使用して IP アドレスを提供することができるサーバーへのアクセス。 Microsoft Teams のルームは、静的な IP アドレスで構成することはできません。
- HTTP ポート 80 と 443 へのアクセス。
- オンプレミスの Skype for Business Server の実装用の[サーバーのポートとプロトコルの要件](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)、および Microsoft Teams または Skype for business Online の[Office 365 url と IP アドレス範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)について説明するように構成された TCP および UDP ポートプリ.

> [!IMPORTANT]
> 有線の 1 Gbps ネットワーク接続を使用して、必要な帯域幅を確保してください。
  
### <a name="certificates"></a>証明書

Microsoft Teams のルームデバイスでは、Exchange Web サービス、Microsoft Teams または Skype for Business、ネットワークの使用状況、認証のための証明書が使用されます。 関連サーバーで公開証明書が使用されている場合 (オンラインとオンプレミスの展開の場合) は、証明書をインストールするために管理者の一部に必要な操作はありません。 一方、証明機関がプライベート CA (オンプレミス展開の場合) である場合は、デバイスでその CA を信頼する必要があります。これは、CA + CA チェーン証明書がデバイスにインストールされていることを意味します。 デバイスをドメインに追加すると、このタスクが自動的に実行されることがあります。
  
その他の Windows クライアントの場合と同じ方法で証明書をインストールします。 
  
> [!NOTE]
> Microsoft Teams のルームで Skype for Business Server を使用できるようにするには、証明書が必要になることがあります。
  
### <a name="proxy"></a>プロキシ

Microsoft Teams のルームは、Windows OS からプロキシ設定を継承するように設計されています。 以下の方法で Windows OS にアクセスします。
  
1. Microsoft Teams の [ルーム] UI で、デバイスのローカル管理者のパスワードを求められる [設定] 歯車アイコンをクリックします (既定のパスワードは**sfb**です)。
2. [**設定**] をタップし、[ **Windows へ移動**] をタップして、[管理者に移動] をタップしてから、[**管理者**]**を**クリックします (コンピューターがドメインに参加している場合は **、[他のユーザー** ] を選び、次に使用します)。ユーザー名として .\admin を指定します。
3. [ **Windows の検索**] ボックスの左下にある [regedit] (画面をクリックするか右クリックして、[**管理者として実行**] を選びます) に入力します。
4. HKEY_USERS フォルダーをクリックします (マシン ユーザー SID の一覧が表示されます)。ルート フォルダー HKEY_USERS が選択されていることを確認します。
       
5. [ファイル] をクリックし、[ハイブの読み込み] を選択し**ます。**
6. **C:\Users\Skype**フォルダーを参照し、[ファイル名] ボックスに「ntuser.dat」と入力して、[開く] をクリックします。

7. 新しくロードされたハイブのキー名を入力するように求められます。Skype に入力します (Skype ユーザのレジストリ設定が表示されます)。
 
8. Skype キーを開き、HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet 設定を参照して、次の設定が入力されていることを確認します。 
    
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    
    "MigrateProxy"=dword:00000001
    
    "ProxyEnable"=dword:00000001
    
    "ProxyServer"="xx.xx.xx.xx:8080"
    
    ProxyServer が存在しない場合は、このキーを文字列として追加し、xx.xx.xx.xx:8080 をプロキシ サーバーの IP/ホストとポートに変更する必要があります。
    
9. 変更が完了したら、Skype ユーザキー (Skype のルートフォルダ) を強調表示して、レジストリファイルメニューから「ハイブをアンロード」を選択します (確認のメッセージが表示されます- **「はい**」を選択します)。
    
10. これで、レジストリ エディターを閉じて、Windows の検索ボックスに logoff と入力できます。
    
11. サインイン画面に戻り、**Skype** ユーザーを選択します。 これまでのすべての手順が成功した場合、Microsoft Teams の会議室のデバイスは正常にサインインします。
    
このアプリケーションを使用するには、以下に説明されているエンドポイントに接続できる必要があります。IP アドレスを表示するには、トラフィックのフローを説明する表の下にある [IP アドレス] セクションを展開します。
  
**ファイアウォール プロキシのホスト名/ポートの例**

|用途|ソースまたは資格情報|発信元ポート|宛先|CDN|ExpressRoute for Office 365|送信先 IP アドレス|送信先ポート|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|認証と ID  <br/> |「 [Office 365 の認証と id」を](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity)ご覧ください。 <br/> |||
|ポータルと共有  <br/> |「 [Office 365 ポータルと共有」を](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity)参照してください。 <br/> |||
|SIP 信号  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |短いポート  <br/> |\*contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype for Business の IP 範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|永続共有オブジェクト モデル (PSOM) 接続 Web 会議  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |短いポート  <br/> |\*contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype for Business の IP 範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|HTTPS ダウンロード  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |短いポート  <br/> |\*contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype for Business の IP 範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|オーディオ  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |TCP/UDP 50,000-50019  <br/> |\*contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype for Business の IP 範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443、UDP 3478、TCP/UDP 50,000-59,999  <br/> |
|ビデオ  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |TCP/UDP 50,020-50039  <br/> |\*contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype for Business の IP 範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443、UDP 3478、TCP/UDP 50,000-59,999  <br/> |
|デスクトップ共有  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |TCP/UDP 50,040-50059  <br/> |\*contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype for Business の IP 範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443、50,000-59,999  <br/> |
|iOS デバイス上の Lync Mobile 2010 向け Lync Mobile プッシュ通知。Android、Nokia Symbian、Windows Phone モバイル デバイスの場合、これは必要ありません。  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |短いポート  <br/> |\*contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype for Business の IP 範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Skype テレメトリ  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |短いポート  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |なし  <br/> |いいえ  <br/> |該当なし  <br/> |TCP 443  <br/> |
|Skype クライアントのヒント  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |短いポート  <br/> |quicktips.skypeforbusiness.com  <br/> |いいえ  <br/> |いいえ  <br/> |該当なし  <br/> |TCP 443  <br/> |
   
> [!NOTE]
> contoso.com および broadcast.skype.com のワイルドカードは、Office 365 専用で使用されるノードの長いリストを表しています。 
  
### <a name="create-provisioning-packages"></a>プロビジョニング パッケージを作成する

プロビジョニングパッケージを使って、Exchange Server または Office 365 への認証を行います。
  
### <a name="admin-group-management"></a>管理グループの管理

ドメインの参加後、ドメイン内の Widonws PC の場合と同じ方法で、グループ ポリシーまたはローカルのコンピュータの管理を使用して、ローカル管理者としてセキュリティ グループを設定できます。 そのセキュリティ グループのどのメンバーでも、各自の資格情報を入力して設定をロック解除することができます。
  
> [!NOTE]
> Microsoft Teams Rooms デバイスがドメインとの信頼関係を失った場合 (たとえば、Microsoft Teams Rooms をドメインに参加させた後にドメインから削除した場合)、デバイスを認証して設定を開くことはできません。 回避策では、ローカルの管理者アカウントでログインします。 
  
## <a name="local-accounts"></a>ローカル アカウント

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft Teams の会議室のローカルユーザーアカウント

通常、デバイス アカウントではパスワードを使用しません。 パスワードを指定することは可能ですが、パスワードが期限切れとなった場合にユーザーがコンソール アプリケーションケーションからロックアウトされる可能性などの因果関係があります。 その結果として、管理者は、パスワードが期限切れにならないようにする必要があります。
  
### <a name="admin---local-administrator-account"></a>"Admin" - ローカル管理者アカウント

Microsoft Teams 会議室の既定のパスワードは、"sfb" に設定されています。 Windows の [設定\> ] に移動して、パスワードをローカルで変更するには、windows または AutoUnattend ファイル (Windows システムイメージマネージャーを使用して、xml ファイルに変更を加えます) を選びます。
  
> [!CAUTION]
> Microsoft Teams の会議室のパスワードはできるだけ早く変更してください。 
  
ドメイン管理者をローカル管理者として設定したグループ ポリシーを設定することで、ローカル管理者のパスワードを管理することもできます。
  
セットアップ中に、ローカル管理者パスワードの選択は含まれません。
  
### <a name="machine-account"></a>コンピューター アカウント

他の Windows デバイスと同じように、PC 名の名前を変更するに\>は\> 、[PC 名の変更に関する設定] を右クリックします。
  
 ドメインに参加した後でコンピューターの名前を変更するには、[コンピューターの名前の変更] コマンドの後にコンピューターの新しい名前を指定します。
  
## <a name="see-also"></a>関連項目

[Microsoft Teams のルームを計画する](skype-room-systems-v2-0.md)

[Microsoft Teams の会議室の要件](requirements.md)
  
[Microsoft Teams ルームの展開](room-systems-v2.md)
  
[Microsoft Teams 室コンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](skype-room-systems-v2.md)
