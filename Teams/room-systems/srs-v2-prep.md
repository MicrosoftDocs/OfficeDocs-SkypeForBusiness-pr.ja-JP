---
title: 環境を準備します。
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection: M365-voice
description: この資料では、マイクロソフト チームの会議室を展開するためのインフラストラクチャの準備作業について説明します。
ms.openlocfilehash: b1830ba68b61c322b6eeef95f29b1e72d2b93303
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865015"
---
# <a name="prepare-your-environment"></a>環境を準備する

このセクションには、すべての Microsoft チームの会議室の機能を使用できるように、環境を準備するための手順の概要が含まれます。
  
1. 各マイクロソフト チームの会議室のコンソールのデバイスのアカウントを準備します。 詳細については、[マイクロソフト チームの部屋の配置](room-systems-v2.md)を参照してください。
    
2. デバイスが使用する、正常に動作しているネットワーク/インターネット接続があることを確認します。 
    
   - DHCP を使用して IP アドレスを受信できる必要があります。 (単位の最初の起動時に、静的 IP アドレスを持つ Microsoft チームの会議室を構成することはできませんが、その後デバイス上または上位のスイッチまたはルータのデバイスに静的 IP を構成する可能性があります)。
    
   - これは、他メディアの通常のポートを開く) を開き、これらのポートが必要です。
    
   - HTTPS: 443
    
   - HTTP: 80
    
   - プロキシを介してネットワークが動作している場合は、プロキシのアドレスまたはスクリプトの情報も必要です。
    
     > [!NOTE]
     > Microsoft Teams Rooms は、HDMI インジェストの機能 (ビデオ、オーディオ) に関する問題を引き起こすことが確認されている、HDCP 入力をサポートしていません。 Microsoft Teams Rooms に接続されたスイッチの HDCP オプションがオフになっていることを必ず確認してください。 
  
3. エクスペリエンスを改善するために、マイクロソフトではデータを収集しています。 データを収集するために、以下のサイトをホワイトリストに記載しておく必要があります。
    
   - 「遠隔測定」クライアントのエンドポイント。https://vortex.data.microsoft.com/
    
   - 「遠隔測定」の設定の終了点:https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>デバイス アカウントを作成してテストする

*デバイスのアカウント*は、ビジネス用の Skype を有効にして、予定表のように、Exchange の機能にアクセスするマイクロソフト チームの会議室のクライアントが使用しているアカウントです。 詳細については、[マイクロソフト チームの部屋の配置](room-systems-v2.md)を参照してください。
  
### <a name="check-network-availability"></a>ネットワークの状態をチェックする

正常に機能するためにマイクロソフト チームの会議室のデバイスにこれらの要件を満たしているワイヤード (有線) ネットワークへのアクセスが必要です。
  
- Active Directory または Azure Active Directory (Azure AD) インスタンスと、Microsoft Exchange および Skype for Business Server へのアクセス。
- DHCP を使用して IP アドレスを提供することができるサーバーへのアクセス。 マイクロソフト チームの会議室は、静的 IP アドレスを構成できません。
- HTTP ポート 80 と 443 へのアクセス。
- TCP および UDP のポートとして構成されている記載されている[サーバーに必要な](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)の設置型の Skype ビジネス サーバー実装では、 [Office 365 の Url と IP アドレスの範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)のマイクロソフトのチームまたはビジネス用の Skype オンライン実装します。

> [!IMPORTANT]
> 有線の 1 Gbps ネットワーク接続を使用して、必要な帯域幅を確保してください。
  
### <a name="certificates"></a>証明書

マイクロソフト チーム室デバイスは、Exchange Web サービス、マイクロソフトのチームまたは Skype のビジネス、ネットワーク使用率、および認証に証明書を使用します。 関連のサーバーがオンラインと一部の設置型展開の場合は、パブリック証明書を使用する場合は、証明書をインストールするのには、管理者側で必要なアクションをさらにいけません。 場合、その一方で、証明機関が (設置型展開では一般的な) プライベート CA を信頼する必要があるデバイスとは、CA と CA が CA チェーンの証明書がデバイスにインストールされています。 デバイスをドメインに追加すると、このタスクが自動的に実行可能性があります。
  
その他の Windows クライアントの場合と同じ方法で証明書をインストールします。 
  
> [!NOTE]
> 証明書は、Skype を使用して、ビジネスのサーバーの Microsoft チームの会議室を持つために必要があります。
  
### <a name="proxy"></a>プロキシ

マイクロソフト チームの会議室は、Windows OS のプロキシ設定を継承するよう設計されています。 以下の方法で Windows OS にアクセスします。
  
1. UI では、マイクロソフト チームの部屋には、場所が表示されます (デフォルトのパスワードは、**デバイス**)、デバイスのローカル管理者のパスワードの設定の歯車アイコンをクリックします。
2. **設定**後に、 **Windows に移動**] ボタンをタップして**管理者サインインするには [移動**] ボタンの順にタップしてと**管理者**] をクリックしてをタップ (コンピューターがドメインに参加している場合 **、その他のユーザー**を選択しを使用して、。 ユーザー名と \admin)。
3. **検索ウィンドウ**の [レジストリ エディターの左の種類を下] ボックスの (どちらか長い画面キーを押しますまたは右クリックし、**管理者として実行**] を選択) します。
4. HKEY_USERS フォルダーをクリックします (マシン ユーザー SID の一覧が表示されます)。ルート フォルダー HKEY_USERS が選択されていることを確認します。
       
5. [ファイル] をクリックし、[**ハイブのロードします**。
6. 参照の**C:\Users\Skype**にフォルダーとファイル名の入力ボックス NTUSER.dat と [開く] ボタンを押します

7. 新しくロードされたハイブは、キー名の入力を要求しますSkype の (すると、Skype のユーザーのレジストリ設定) を入力します。
 
8. Skype キーを開き、[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet の設定を参照し、これらの設定が入力されたことを確認します。 
    
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    
    "MigrateProxy"=dword:00000001
    
    "ProxyEnable"=dword:00000001
    
    "ProxyServer"="xx.xx.xx.xx:8080"
    
    ProxyServer が存在しない場合は、このキーを文字列として追加し、xx.xx.xx.xx:8080 をプロキシ サーバーの IP/ホストとポートに変更する必要があります。
    
9. Skype ユーザー (Skype のルート フォルダー) のキーし、選択の強調表示 (説明の入力を求め確認 - [**はい]** )、レジストリ ファイル] メニューからハイブをアンロードすると、変更が完了した後です。
    
10. これで、レジストリ エディターを閉じて、Windows の検索ボックスに logoff と入力できます。
    
11. サインイン画面に戻り、**Skype** ユーザーを選択します。 以前のすべてのステップが成功した場合マイクロソフト チームの会議室のデバイスはサインインが正常にします。
    
このアプリケーションを使用するには、以下に説明されているエンドポイントに接続できる必要があります。IP アドレスを表示するには、トラフィックのフローを説明する表の下にある [IP アドレス] セクションを展開します。
  
**ファイアウォール プロキシのホスト名/ポートの例**

|用途|ソースまたは資格情報|発信元ポート|宛先|CDN|ExpressRoute for Office 365|送信先 IP アドレス|送信先ポート|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|認証と ID  <br/> |[Office 365 の認証と id](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity)を参照してください。 <br/> |||
|ポータルと共有  <br/> |[Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity)を参照してください。 <br/> |||
|SIP 信号  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |短いポート  <br/> |\*。 contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype ビジネス IP の範囲の](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|永続共有オブジェクト モデル (PSOM) 接続 Web 会議  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |短いポート  <br/> |\*。 contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype ビジネス IP の範囲の](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|HTTPS ダウンロード  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |短いポート  <br/> |\*。 contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype ビジネス IP の範囲の](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|オーディオ  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |TCP/UDP 50,000-50019  <br/> |\*。 contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype ビジネス IP の範囲の](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443、UDP 3478、TCP/UDP 50,000-59,999  <br/> |
|ビデオ  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |TCP/UDP 50,020-50039  <br/> |\*。 contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype ビジネス IP の範囲の](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443、UDP 3478、TCP/UDP 50,000-59,999  <br/> |
|デスクトップ共有  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |TCP/UDP 50,040-50059  <br/> |\*。 contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype ビジネス IP の範囲の](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443、50,000-59,999  <br/> |
|iOS デバイス上の Lync Mobile 2010 向け Lync Mobile プッシュ通知。Android、Nokia Symbian、Windows Phone モバイル デバイスの場合、これは必要ありません。  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |短いポート  <br/> |\*。 contoso.com  <br/> |いいえ  <br/> |はい  <br/> |[Skype ビジネス IP の範囲の](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Skype テレメトリ  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |短いポート  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |なし  <br/> |いいえ  <br/> |該当なし  <br/> |TCP 443  <br/> |
|Skype クライアントのヒント  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |短いポート  <br/> |quicktips.skypeforbusiness.com  <br/> |いいえ  <br/> |いいえ  <br/> |該当なし  <br/> |TCP 443  <br/> |
   
> [!NOTE]
> contoso.com および broadcast.skype.com のワイルドカードは、Office 365 専用で使用されるノードの長いリストを表しています。 
  
### <a name="create-provisioning-packages"></a>プロビジョニング パッケージを作成する

Exchange Server または Office 365 の認証には、プロビジョニング ・ パッケージを使用します。
  
### <a name="admin-group-management"></a>管理グループの管理

ドメインの参加後、ドメイン内の Widonws PC の場合と同じ方法で、グループ ポリシーまたはローカルのコンピュータの管理を使用して、ローカル管理者としてセキュリティ グループを設定できます。 そのセキュリティ グループのどのメンバーでも、各自の資格情報を入力して設定をロック解除することができます。
  
> [!NOTE]
> Microsoft Teams Rooms デバイスがドメインとの信頼関係を失った場合 (たとえば、Microsoft Teams Rooms をドメインに参加させた後にドメインから削除した場合)、デバイスを認証して設定を開くことはできません。 回避策では、ローカルの管理者アカウントでログインします。 
  
## <a name="local-accounts"></a>ローカル アカウント

### <a name="microsoft-teams-rooms-local-user-account"></a>マイクロソフト チーム ルームのローカル ユーザー アカウント

通常、デバイス アカウントではパスワードを使用しません。 パスワードを指定することは可能ですが、パスワードが期限切れとなった場合にユーザーがコンソール アプリケーションケーションからロックアウトされる可能性などの因果関係があります。 その結果として、管理者は、パスワードが期限切れにならないようにする必要があります。
  
### <a name="admin---local-administrator-account"></a>"Admin" - ローカル管理者アカウント

マイクロソフト チーム ルームのデフォルトのパスワードは、「デバイス」に設定されていますいます。 Windows の設定に移動してローカルでは、パスワードを変更することができます\>Windows または AutoUnattend.xml ファイル (xml ファイルに変更を加えるに ADK から Windows システム イメージ マネージャーを使用します) での移動。
  
> [!CAUTION]
> マイクロソフト チームの会議室のパスワードをできるだけ早く変更することを確認します。 
  
ドメイン管理者をローカル管理者として設定したグループ ポリシーを設定することで、ローカル管理者のパスワードを管理することもできます。
  
セットアップ中に、ローカル管理者パスワードの選択は含まれません。
  
### <a name="machine-account"></a>コンピューター アカウント

任意の Windows デバイスと同じようにコンピューター名名前を変更できる設定で右クリックして\>の\>PC の名前を変更します。
  
 ドメインへの参加後、コンピューターの名前を変更したい場合は、コンピューターの新しい名前の後に名前の変更-コンピューターの PowerShell コマンドを使用します。
  
## <a name="see-also"></a>関連項目

[マイクロソフト チームの会議室を計画します。](skype-room-systems-v2-0.md)

[マイクロソフト チームの会議室の要件](requirements.md)
  
[マイクロソフト チームの会議室を配置します。](room-systems-v2.md)
  
[マイクロソフト チームの会議室のコンソールを構成します。](console.md)
  
[Microsoft Teams Rooms を管理する](skype-room-systems-v2.md)
