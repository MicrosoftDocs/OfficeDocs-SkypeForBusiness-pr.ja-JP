---
title: Skype Room Systems バージョン 2 の計画
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
description: この資料では、Skype ルーム システム v2 では、Skype ルーム システムの次世代を展開するため、関連する計画に関する考慮事項について説明します。
ms.openlocfilehash: 3d958c5d07cfafd2eeddd6076182a635cfff19de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-skype-room-systems-v2"></a>Skype Room Systems バージョン 2 の計画
 
この資料では、Skype ルーム システム v2 では、Skype ルーム システムの次世代を展開するため、関連する計画に関する考慮事項について説明します。 
  
 Skype ルーム システム v2 は、ビジネス経験の豊富な共同の Skype 会議室に変換するように設計された、マイクロソフトの最新の会議ソリューションです。 ユーザーは慣れ親しんだ Skype for Business インターフェイスを活用し、IT 管理者は Windows 10 Skype Meeting アプリを簡単に展開および管理することができます。 Skype ルーム システム v2 は、Skype をビジネスの会議室に移動するのにはインストールの容易さの LCD パネルと同様に既存の機器を活用するよう設計されています。
  
Skype ルーム システム v2 では、Skype の会議のユーザー インターフェイスとして機能する専用の UWP アプリケーションを使用します。 Surface Pro 4 または Surface Pro のコンソール モードで実行される (UWP のアプリケーションを展開した後は、デバイス上で実行される唯一のアプリケーション)、ビジネスの実装については、Skype の独自デバイスのアカウントを必要とします。 LCD パネルや比較的安価な周辺機器のカメラのような既存の機器を活用し、および品質の会議室を提供するのにはマイクが発生します。 Windows ストアと Windows の更新プログラムの両方を使用してソフトウェアを更新します。
  
環境の準備を始める前に、必要なハードウェアとソフトウェアがあることを確認します。 詳細については、 [Skype ルーム システム v2 の要件](requirements.md)を参照してください。 
  
> [!NOTE]
> Skype ルーム システム v2 は、使用で Skype ビジネス サーバー 2015 または Skype のオンライン ビジネスの。 Lync Server 2013 のような以前のプラットフォームは、Skype ルーム システム v2 を使用する必要はありません。 
  
Skype ルーム システム v2 は、ビジネス経験の豊富な共同の Skype 会議室に変換するように設計された、マイクロソフトの最新の会議ソリューションです。 ユーザーは慣れ親しんだ Skype for Business インターフェイスを活用し、IT 管理者は Windows 10 Skype Meeting アプリを簡単に展開および管理することができます。 Skype ルーム システム v2 は、Skype をビジネスの会議室に移動するのにはインストールの容易さの LCD パネルと同様に既存の機器を活用するよう設計されています。
  
 **Skype for Business 用**
  
- Skype 会議のワンタッチ参加
    
- 画面を埋め尽くす HD ビデオと HD ワイドバンド オーディオを使用するルーム向けに最適化されたSkype 会議のエクスペリエンス
    
- すべての参加者は、各自希望のデバイスを使用して、どこからでも Skype Meeting に接続することができる
    
- 状態を簡単に表示できるディレクトリから、または通話経由でユーザーを招待する
    
- ルーム内のスタンドアロン会議電話を置き換える Skype for Business PSTN 会議と PSTN 通話をサポート
    
 **どの会議室でも変換**
  
- 中央のテーブル タッチ コントローラーと正面にある大型室内ディスプレイ向けに最適化された専用の Skype 会議アプリ
    
- 正面の室内ディスプレイやプロジェクターで既存の投資を再利用
    
- ちょっとした打ち合わせから、大規模な会議室まで、すべてのタイプのミーティング スペースに対応
    
- Skype for Business の認定オーディオ デバイスとビデオ デバイスはさまざまなサイズのルームで利用可能
    
- ルームおよび Skype 会議でデスクトップ共有を投影する組み込みの有線取り込み
    
- ルーム オーディオとビデオの USB デバイス U1 を満たすためのアプリケーションでユーザーの選択
    
- デュアル画面対応 (従来のシステムのパリティ) U2
    
- Themability (組み込みのテーマとユーザー設定のテーマを設定する機能) U2
    
 **展開が容易、管理が簡単**
  
- 室内でユーザーを検出すると自動的ディスプレイをオンにする Always-on アプライアンス
    
- UWP (ユニバーサル Windows プラットフォーム) Skype 会議アプリの展開と更新が簡単
    
- Windows AppLocker で Skype 会議アプリへのデバイスをロック ダウン
    
- Intune および SCCM (MDM) 経由で Windows 10 Enterprise デバイスとして監視および管理
    
- エンタープライズ レベルの信頼性
    
- 慣れ親しんだ Skype ユーザー インターフェイスのためにトレーニングの労力が少ない
    
- Surface Pro 4 タブレット上で動作
    
- ルーム コンソールのステータスがマイクロソフトの運用管理スイートを使用しているお客様のレポートを統合 ( [OMS を使用して Skype ルーム システムの計画 v2 の管理](oms-management.md)を参照してください) U1
    
- パブリック フィードバックする機能が U2 を構築します。
    
- 会議の結合の信頼性 U2 の周りの改善された遠隔測定
    
- U2 を報告する追加の OMS
    
- デバイスをリモートで構成する IT 管理者の能力 U2
    <!--  - Front-of-Room UX shows room details pre-meeting U2  -->
- U3 Surface Pro のタブレット上で実行します。
    
- Windows 10 企業の作成元の更新プログラム (英語の言語をビルド 1703) U3 をサポートしています。
    
- [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system)のサポート ハードウェア U3 のドッキングします。
    
- 環境制御 (Crestron) U3 の OEM サポート
    
- [ポリコム MSR シリーズ](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)のサポートは、hardwareU4 を固定します。
    
- [Logitech (ロジクール) Brio](https://www.logitech.com/en-us/product/brio)U4 のサポート

- [Lenovo ハブ 500](https://www3.lenovo.com/us/en/hub500)U5 のサポートは、ハードウェアをドッキングします。  
    
U1 の更新 1 (ソフトウェアのバージョンで導入された機能 2.0.2.0)。
  
更新 2 (ソフトウェアのバージョンで導入された機能の U2- 3.0.6.0)。 
  
U3 機能更新 3 (ソフトウェアのバージョンで導入されました。 3.0.12.0)。 
  
更新 4 (ソフトウェアのバージョンで導入された機能の u4 の場合- 3.0.15.0)。 

更新 5 (ソフトウェアのバージョンで導入された機能の U5- 3.1.98.0)。 
  
## <a name="preparing-your-skype-for-business-environment"></a>Skype for Business 環境の準備

このセクションには、すべての Skype ルーム システム v2 の機能を使用できるように、環境を準備するのに必要な手順の概要が含まれます。
  
1. 各 Skype ルーム システム v2 のコンソールのデバイスのアカウントを準備します。 詳細については、 [Skype ルーム システムの配置のバージョン 2](../../deploy/deploy-clients/room-systems-v2.md)を参照してください。
    
2. デバイスが使用する、正常に動作しているネットワーク/インターネット接続があることを確認します。 
    
  - DHCP を使用して IP アドレスを受信できる必要があります (注: 最初のユニットの起動時に静的 IP アドレスを持つ Skype ルーム システム v2 を構成することはできません)
    
  - 次のポートが開かれている必要があります (Skype for Business メディアの通常のポートも開かれている必要があります)。
    
  - HTTPS: 443
    
  - HTTP: 80
    
  - プロキシを介してネットワークが動作している場合は、プロキシのアドレスまたはスクリプトの情報も必要です。
    
    > [!NOTE]
    > V2 は HDMI での問題を引き起こすことが確認されています、HDCP の入力をサポートしていません、Skype ルーム システムは、機能 (ビデオ、オーディオ) を取り込みします。 Skype ルーム システム v2 に接続されたスイッチが HDCP 機能をオフにできるように注意します。 
  
3. エクスペリエンスを改善するために、マイクロソフトではデータを収集しています。データを収集するために、以下のサイトをホワイトリストに記載しておく必要があります。
    
  - 「遠隔測定」クライアントのエンドポイント。https://vortex.data.microsoft.com/
    
  - 「遠隔測定」の設定の終了点:https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>デバイス アカウントを作成してテストする

*デバイスのアカウント*は、ビジネス用の Skype を有効にして、予定表のように、Exchange の機能にアクセスする Skype ルーム システムのバージョン 2 のクライアントが使用しているアカウントです。 詳細については、 [Skype ルーム システムの配置のバージョン 2](../../deploy/deploy-clients/room-systems-v2.md)を参照してください。
  
### <a name="check-network-availability"></a>ネットワークの状態をチェックする

正常に機能するために Skype ルーム システムのバージョン 2 のデバイスにこれらの要件を満たしているワイヤード (有線) ネットワークへのアクセスが必要です。
  
- Active Directory または Azure Active Directory (Azure AD) インスタンスと、Microsoft Exchange および Skype for Business Server へのアクセス。
    
- DHCP を使用して IP アドレスを提供することができるサーバーへのアクセス。 Skype ルーム システム v2 は、静的 IP アドレスを構成できません。
    
- HTTP ポート 80 と 443 へのアクセス。
    
- TCP および UDP ポートの[Lync Server 2013 のポート要件](https://technet.microsoft.com/en-us/library/gg398798%28v=ocs.15%29.aspx)をオンプレミス Skype ビジネスの実装、または[Office 365 の Url と IP アドレスの範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)の Skype のオンラインでのビジネスの説明に従って構成します。
    
> [!IMPORTANT]
> 有線の 1 Gbps ネットワーク接続を使用して、必要な帯域幅を確保してください。 
  
### <a name="certificates"></a>証明書

Skype ルーム システム v2 デバイスは、Exchange Web サービス、Skype のビジネス、ネットワーク使用率、および認証に証明書を使用します。 関連のサーバーがオンラインと一部の設置型展開の場合は、パブリック証明書を使用する場合は、証明書をインストールするのには、管理者側で必要なアクションをさらにいけません。 場合、その一方で、証明機関が (設置型展開では一般的な) プライベート CA を信頼する必要があるデバイスとは、CA と CA が CA チェーンの証明書がデバイスにインストールされています。 デバイスをドメインに追加すると、このタスクが自動的に実行可能性があります。
  
その他の Windows クライアントの場合と同じ方法で証明書をインストールします。 
  
> [!NOTE]
> Skype ルーム システム v2 のビジネスのサーバーに Skype を使用するために証明書を必要があります。 
  
### <a name="proxy"></a>プロキシ

Skype ルーム システム v2 は、Windows OS のプロキシ設定を継承するよう設計されています。 以下の方法で Windows OS にアクセスします。
  
1. Skype ルーム システム v2 UI で、場所が表示されます (デフォルトのパスワードは、「デバイス」) デバイスのローカル管理者のパスワードの設定の歯車アイコンをクリックします。
    
2. 後に"Windows へ移動] ボタンをタップしての順にタップして、[設定] をタップして、"管理者の記号をで」ボタンと、[管理者] ボタンをクリックして (「その他のユーザー」を選択しを使用してコンピューターがドメインに参加している場合。 \admin ユーザー名と)。
    
3. 検索ウィンドウでは、regedit (長いキーを押して画面か、右クリックし、[管理者として実行] を選択) の下の左型をボックスします。
    
4. HKEY_USERS フォルダーをクリックします (マシン ユーザー SID の一覧が表示されます)。ルート フォルダー HKEY_USERS が選択されていることを確認します。
    
    新しくロードされたハイブは、キー名の入力を要求しますSkype の (すると、Skype のユーザーのレジストリ設定) を入力します。
    
5. [ファイル] をクリックし、[ハイブの読み込み] を選択します。
    
6. フォルダー「C:\Users\Skype」を参照して、[ファイル名] ボックスに NTUSER.dat を入力し、[開く] ボタンを押します。
    
7. Skype キーを開き、[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet の設定を参照し、これらの設定が入力されたことを確認します。 
    
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    
    "MigrateProxy"= dword:00000001
    
    "ProxyEnable"= dword:00000001
    
    "ProxyServer"="xx.xx.xx.xx:8080"
    
    ProxyServer が存在しない場合は、このキーを文字列として追加し、xx.xx.xx.xx:8080 をプロキシ サーバーの IP/ホストとポートに変更する必要があります。
    
8. Skype ユーザー (Skype のルート フォルダー) のキーし、選択の強調表示 (説明の入力を求め確認 - [**はい]** )、レジストリ ファイル] メニューからハイブをアンロードすると、変更が完了した後です。
    
9. これで、レジストリ エディターを閉じて、Windows の検索ボックスに logoff と入力できます。
    
10. サインイン画面に戻り、**Skype** ユーザーを選択します。 以前のすべてのステップが成功した場合 Skype ルーム システムのバージョン 2 のデバイスはサインインが正常にします。
    
このアプリケーションを使用するには、以下に説明されているエンドポイントに接続できる必要があります。IP アドレスを表示するには、トラフィックのフローを説明する表の下にある [IP アドレス] セクションを展開します。
  
**ファイアウォール プロキシのホスト名とポートの例**

|**目的**|**ソースまたは資格情報**|**発信元ポート**|**宛先**|**CDN**|**Office 365 の ExpressRoute**|**宛先 IP**|**宛先ポート**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|認証と ID  <br/> |[Office 365 の認証と id](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity)を参照してください。 <br/> |||
|ポータルと共有  <br/> |[Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity)を参照してください。 <br/> |||
|SIP 信号  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |短いポート  <br/> |\*。 contoso.com  <br/> |なし  <br/> |あり  <br/> |[Skype ビジネス IP の範囲の](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|永続共有オブジェクト モデル (PSOM) 接続 Web 会議  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |短いポート  <br/> |\*。 contoso.com  <br/> |なし  <br/> |あり  <br/> |[Skype ビジネス IP の範囲の](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|HTTPS ダウンロード  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |短いポート  <br/> |\*。 contoso.com  <br/> |なし  <br/> |あり  <br/> |[Skype ビジネス IP の範囲の](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|オーディオ  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |TCP/UDP 50,000-50019  <br/> |\*。 contoso.com  <br/> |なし  <br/> |あり  <br/> |[Skype ビジネス IP の範囲の](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443、UDP 3478、TCP/UDP 50,000-59,999  <br/> |
|ビデオ  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |TCP/UDP 50,020-50039  <br/> |\*。 contoso.com  <br/> |なし  <br/> |あり  <br/> |[Skype ビジネス IP の範囲の](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443、UDP 3478、TCP/UDP 50,000-59,999  <br/> |
|デスクトップ共有  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |TCP/UDP 50,040-50059  <br/> |\*。 contoso.com  <br/> |なし  <br/> |あり  <br/> |[Skype ビジネス IP の範囲の](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443、50,000-59,999  <br/> |
|iOS デバイス上の Lync Mobile 2010 向け Lync Mobile プッシュ通知。Android、Nokia Symbian、Windows Phone モバイル デバイスの場合、これは必要ありません。  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |短いポート  <br/> |\*。 contoso.com  <br/> |なし  <br/> |あり  <br/> |[Skype ビジネス IP の範囲の](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Skype テレメトリ  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |短いポート  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |いいえ  <br/> |いいえ  <br/> |該当なし  <br/> |TCP 443  <br/> |
|Skype クライアントのヒント  <br/> |クライアント コンピューターまたはログオン ユーザー  <br/> |短いポート  <br/> |quicktips.skypeforbusiness.com  <br/> |いいえ  <br/> |いいえ  <br/> |該当なし  <br/> |TCP 443  <br/> |
   
> [!NOTE]
> contoso.com および broadcast.skype.com のワイルドカードは、Office 365 専用で使用されるノードの長いリストを表しています。 
  
### <a name="create-provisioning-packages"></a>プロビジョニング パッケージを作成する

プロビジョニング パッケージは、Exchange Server や Skype for Business Server の認証に使用します。
  
### <a name="admin-group-management"></a>管理グループの管理

ドメインの参加後、ドメイン内の Widonws PC の場合と同じ方法で、グループ ポリシーまたはローカルのコンピュータの管理を使用して、ローカル管理者としてセキュリティ グループを設定できます。 そのセキュリティ グループのどのメンバーでも、各自の資格情報を入力して設定をロック解除することができます。
  
> [!NOTE]
> Skype ルーム システム v2 デバイスで (たとえば、ドメインからドメインに参加しては、その後 Skype ルーム システム v2 を削除する場合) ドメインとの信頼関係が失われた場合にデバイスを認証し、設定を開くことはできません。 回避策として、ローカル管理アカウントでログインできます。 
  
## <a name="local-accounts"></a>ローカル アカウント

### <a name="skype-room-systems-local-user-account"></a>Skype Room Systems ローカル ユーザー アカウント

通常、デバイス アカウントではパスワードを使用しません。 パスワードを指定することは可能ですが、パスワードが期限切れとなった場合にユーザーがコンソール アプリケーションケーションからロックアウトされる可能性などの因果関係があります。 その結果として、管理者は、パスワードが期限切れにならないようにする必要があります。
  
### <a name="admin---local-administrator-account"></a>"Admin" - ローカル管理者アカウント

Skype ルーム システム v2 のデフォルトのパスワードは、「デバイス」に設定されていますいます。 Windows の設定に移動してローカルでは、パスワードを変更することができます\>Windows または AutoUnattend.xml ファイル (xml ファイルに変更を加えるに ADK から Windows システム イメージ マネージャーを使用します) での移動。
  
> [!CAUTION]
> 必ず Skype ルーム システム v2 パスワードをできるだけ早く変更してください。 
  
ドメイン管理者をローカル管理者として設定したグループ ポリシーを設定することで、ローカル管理者のパスワードを管理することもできます。
  
ローカルの管理者パスワードは、セットアップ中には選択肢に含まれているではありません。
  
### <a name="machine-account"></a>コンピューター アカウント

任意の Windows デバイスと同じようにコンピューター名名前を変更できる設定で右クリックして\>の\>PC の名前を変更します。
  
 ドメインへの参加後、コンピューターの名前を変更したい場合は、コンピューターの新しい名前の後に名前の変更-コンピューターの PowerShell コマンドを使用します。
  
## <a name="see-also"></a>関連項目

#### 

[Skype ルーム システム v2 の要件](requirements.md)
  
[Skype の部屋を配置するシステム v2](../../deploy/deploy-clients/room-systems-v2.md)
  
[Skype ルーム システム v2 のコンソールを構成します。](../../deploy/deploy-clients/console.md)
  
[Skype ルームの管理システム v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

