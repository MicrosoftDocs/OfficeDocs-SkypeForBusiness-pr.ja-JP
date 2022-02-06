---
title: Skypeシステムの管理性とツール
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: このトピックでは、ルーム システムの管理ツールSkype説明します。
---

# <a name="skype-room-system-manageability-and-tools"></a>Skypeシステムの管理性とツール
 
このトピックでは、ルーム システムの管理ツールSkype説明します。
  
## <a name="administrative-portal"></a>管理ポータル

オンプレミスSkype for Business Serverの場合は、Skype Room System 管理ポータルを使用して、組織内の Skype ルーム システム展開を積極的に管理および監視できます。
  
詳細については、次の記事を参照してください。
  
- [SRS v1 管理 Web ポータルをサーバーに展開Skype for Business Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Exchangeチェックリスト

- 自動検出がセットアップされ、内部 DNS A/CNAME RECORD が使用できるのを確認 autodiscover.domain.com。
    
- Ping の自動検出 (Ping の自動検出など Autodiscover.contoso.com)。
    
- Microsoft Connectivity Analyzer ツールを使用して自動検出サービスをテストします。 最初のテストを選択します。"ユーザーと一緒にログオンOffice Outlook。
    
- 会議室に既にリソース メールボックスがある場合は、Skype (ページの下部にあるスクリプトの例) に対してこのアカウントを拡張します。
    
## <a name="skype-for-business-checklist"></a>Skype for Businessチェックリスト

- 次のツールを実行します。
    
  - Skype for Businessベスト プラクティス アナライザー     
  - Skype for Business正常性分析ツール (Excel)    
  - Skype for Business Connectivity Analyzer 32 ビットまたは 64 ビット
    
- 「[新しいトラブルシューティングと分析に役立つツール」を参照Office 365](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365)。 Web Apps サーバーにSkype for Business、Officeクライアントを使用してPowerPointデッキをSkype for Businessします。
    
- 会議室にリソース メールボックスが既に存在する場合は、そのメールボックスを有効Skype for Business。
    
- 必要に応じて、システムの DID (電話番号) を要求ミーティング ルーム、Active Directory ツールの [全般電話] フィールドを更新します。
    
## <a name="network"></a>ネットワーク

- ルーム システムに対して有線ネットワーク接続Skypeしてください。
    
- 詳細については、「ネットワーク計画ガイド」をSkype for Business。
    
- パートナーからSkype for Businessネットワーク評価を要求Skype for Businessします。
    
- 正常性分析ツール (Skype for Business) でキャプチャされたパフォーマンス データExcel。
    
- ネットワーク分析ツールを実行します。
    
- プレコール診断ツールを実行します。
    
## <a name="skype-room-system-security"></a>Skype ルーム システム のセキュリティ

Skype Room System は、Skype for Business セキュリティ モデル、権限管理、SCOM などの管理ツールを使用して、Windows 展開に完全に統合できる組み込みシステムです。 以下の機能があります。
  
- ユーザー モードでのディスク書き込みを防止する書き込みフィルター 
    
- 承認されていないアプリが実行されるのを防ぐためのアプリ ロッカー。 ユーザー モードでは、すべての USB ポートが無効になります。
    
  - 標準のアプリや閲覧者は、Skypeシステム ハードウェアに存在します。 すべてのコンテンツは、HTTP または RDP プロトコルを介してレンダリングされます。
    
  - アプライアンス PC は、埋め込Windows 7 オペレーティング システムを実行します。 デバイスを含むすべてのハードウェアは、OEM パートナーによって提供されます。
    
  - オプションの Active Directory ドメイン サービスへのドメイン参加 (AD DS) で、ローカル セキュリティ アカウントの管理と制御を有効にします。
    
- ローカル管理センターを使用してローカル管理者アカウントSkype for Businessすることもできます。
    
- Skypeは、標準の Microsoft Update プロセスを通じて更新されます。
    
- Skypeルーム システムは、ユーザーに接続Skype for Business。
    
  - Skype for Businessは、すべての通信モードでエンドツーエンドの暗号化と承認を使用します。
    
  - Skypeシステムは、セキュリティSkype for Businessコンプライアンス標準をサポートします。 詳細[については、「Plan for Business Server Skypeセキュリティを](../../plan-your-deployment/security/security.md)計画する」を参照してください。
    
## <a name="license"></a>ライセンス

ソフトウェアのライセンス認証にKMS確認します。 その場合は、クライアント キーをチェックまたは追加するSkype for Business必要KMS場合があります。 クライアントを使用していないKMS、クライアント MAK のボリューム ライセンス キー Skype for Business要求します。
  
## <a name="license-keys"></a>ライセンス キー

Skypeルーム システムは、バックグラウンドSkype for Businessデスクトップ クライアントを実行します。 ルーム Skypeがドメイン メンバーである場合は、そのルーム システムがKMS。 (ボリューム ライセンス が設定されている場合KMS自動的にアクティブ化されます)。 ボリューム ライセンスには MAK も用意され、xxxxx-xxxxx-xxxxx-xxxxx-xxxxx を表示する場合に入力します。 (MAK を使用してアクティブ化するにはインターネット アクセスが必要ですが、ライセンス認証はKMS)。 詳細については、「2013 年のボリューム ライセンス認証」を参照Office。
  
- MAK キーを入力するには、OEM \> 設定SRS ライセンス ツールに移動します。 [状態の確認] をクリックします。 状態が "製品がアクティブ化されていません" と表示された場合は、キーを入力します。
    
- ライセンス認証中に「ソフトウェア ライセンス サービスからプロダクト キーが無効だと報告されました」というエラーが表示される場合は、次の確認を行います。
    
  - キーが正しく入力されました。
    
  - 別のキーではなくSkype for Business MAK キーを入力しました。
    
  - システムはインターネットにアクセスできます。
    
- 電話でライセンス認証できますが、最初に SRS ライセンス ツールを使用してライセンス認証を試みた必要があります。 電話でアクティブにするには、テスト会議を開始します (短すぎるテスト通話ではありません)。 [ライセンス認証Office] で、[電話のライセンス認証] を選択し、Microsoft に電話し、長い番号を入力して、応答を入力します。
    
## <a name="certificate-authority"></a>証明機関

Web Apps Server 2013 証明書Office発行に使用する証明機関の HTTP パスが証明書失効リスト プロパティに含まれているか確認します。
  
証明書ファイル (.crt) を使用している場合は、Skype ルーム システムにインポートSkype for Business Server。 CA サーバーの CertEnroll 共有、またはドメインに参加している PC の信頼されたルート フォルダーから簡単に取得できます。
  
## <a name="certificates"></a>証明書

証明機関に証明書失効リストの http パスが含されていないことを確認します。 含めない場合は、CA を更新して 1 つを含める。
  
[システムと証明書マネージャー] の下にある Skypeルーム システムの管理者セットアップ設定\>インストールします。 内部証明書のEnterpriseルート CA が必要です。
  
必要な証明書を取得する方法の 1 つは、証明書を発行した CA を検出する方法です。 [Skype for Business Server] の PC でSkype for Business、[ツール \> ダイヤルイン会議設定] \> をクリック設定。 これにより、内部証明書を発行した CA によってセキュリティで保護された Web ページが開きます。 ブラウザーのアドレス バーの [ロック] アイコンをクリックして、セキュリティ レポートを表示します。 [証明書の表示] をクリックし、CRL 配布ポイント プロパティを確認します。 2 番目の CN パラメーターは、CA のサーバー名である必要があります。 次に、Windows \\\\< CA Server Name \>CertEnroll のエクスプローラーを開きます。 2 つの .crl ファイルと .crt ファイルをフラッシュ ドライブにコピーし、SMART ボードの左側に置きます。
  
.crt ファイルを [信頼できる部屋証明機関] フォルダー Skype下のルーム システムにインポートします。
  
中間証明書機関フォルダーの下Skypeルーム システムの .crl ファイルをインポートします。 (ファイルを表示するには、証明書マネージャーのファイル拡張子フィルターを .crl に変更する必要があります)。
  
注: Web Apps 2013 Officeサーバーは、Web Apps 2013 サーバーと同じ CA を共有Skype for Business。 共有できない場合は、会議でPowerPoint共有できます。 IT に確認し、上記のように CA ネットワーク共有 CertEnroll から CRT ファイルと CRL ファイルを取得します。 
  
ドメイン メンバーシップは、Skype Room System を Windows システムとして扱い、証明書の側面の一部を Active Directory に依存できるので、いくつかのことを簡略化できます。 ただし、手動で管理する方が最適です。
