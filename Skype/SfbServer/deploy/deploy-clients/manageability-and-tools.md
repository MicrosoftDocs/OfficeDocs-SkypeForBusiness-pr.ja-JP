---
title: Skype Room System の管理性とツール
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Skype Room System の管理ツールの詳細については、このトピックを参照してください。
ms.openlocfilehash: 81adbb93c71abc201d9099d86e8414a524d85dff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093551"
---
# <a name="skype-room-system-manageability-and-tools"></a>Skype Room System の管理性とツール
 
Skype Room System の管理ツールの詳細については、このトピックを参照してください。
  
## <a name="administrative-portal"></a>管理ポータル

Skype for Business Server オンプレミス展開の場合、Skype Room System 管理ポータルを使用して、組織内の Skype Room System の展開を積極的に管理および監視できます。
  
詳細については、次の記事を参照してください。
  
- [Skype for Business Server で SRS v1 管理 Web ポータルを展開する](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Exchange チェックリスト

- 自動検出がセットアップされ、内部 DNS A/CNAME RECORD が使用できるのを確認 autodiscover.domain.com。
    
- Ping の自動検出 (Ping の自動検出など Autodiscover.contoso.com)。
    
- Microsoft Connectivity Analyzer ツールを使用して自動検出サービスをテストします。 最初のテストを選択します。"Outlook でログオンOfficeします。
    
- 会議室に既にリソース メールボックスがある場合は、このアカウントを Skype Room System 用に拡張します (ページの下部にあるスクリプトの例)。
    
## <a name="skype-for-business-checklist"></a>Skype for Business チェックリスト

- 次のツールを実行します。
    
  - Skype for Business のベスト プラクティス アナライザー     
  - Skype for Business Health Analysis Tool (Excel)    
  - Skype for Business Connectivity アナライザー 32 ビットまたは 64 ビット
    
- [「365 用の便利な新しいトラブルシューティングと分析ツールOffice確認します](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365)。 Skype for Business プールと Web Apps サーバー Officeし、Skype for Business クライアントを使用して PowerPoint デッキを共有できます。
    
- 会議室にリソース メールボックスが既に存在する場合は、Skype for Business で有効にします。
    
- 必要に応じて、会議室システムの DID (電話番号) を要求し、Active Directory ツールの [一般電話] フィールドを更新します。
    
## <a name="network"></a>ネットワーク

- Skype Room System のワイヤード (有線) ネットワーク接続が確立されている必要があります。
    
- Skype for Business のネットワーク計画ガイドを参照してください。
    
- Skype for Business パートナーから Skype for Business ネットワーク評価を要求します。
    
- Skype for Business Health Analysis Tool (Excel) でキャプチャされたパフォーマンス データを読み取ります。
    
- ネットワーク分析ツールを実行します。
    
- プレコール診断ツールを実行します。
    
## <a name="skype-room-system-security"></a>Skype Room System Security

Skype Room System は、Skype for Business セキュリティ モデル、権限管理、SCOM などの管理ツールを使用して、Windows 展開に完全に統合できる組み込みシステムです。 以下の機能があります。
  
- ユーザー モードでのディスク書き込みを防止する書き込みフィルター 
    
- 承認されていないアプリが実行されるのを防ぐためのアプリ ロッカー。 ユーザー モードでは、すべての USB ポートが無効になります。
    
  - 標準のアプリや閲覧者は Skype Room System ハードウェアに存在します。 すべてのコンテンツは、HTTP または RDP プロトコルを介してレンダリングされます。
    
  - アプライアンス PC は、Windows Embedded Standard 7 オペレーティング システムを実行します。 デバイスを含むすべてのハードウェアは、OEM パートナーによって提供されます。
    
  - オプションの Active Directory ドメイン サービスへのドメイン参加 (AD DS) で、ローカル セキュリティ アカウントの管理と制御を有効にします。
    
- また、Skype for Business 管理センターを使用してローカル管理者アカウントを管理することもできます。
    
- Skype Room System は、標準の Microsoft Update プロセスを通じて更新されます。
    
- Skype Room System は Skype for Business に接続します。
    
  - Skype for Business は、すべての通信モードでエンドツーエンドの暗号化と承認を使用します。
    
  - Skype Room System は、Skype for Business のセキュリティとコンプライアンスの標準をサポートします。 詳細 [については、「Plan for security in Skype For Business Server」](../../plan-your-deployment/security/security.md) を参照してください。
    
## <a name="license"></a>ライセンス

ソフトウェアのアクティブ化に KMS を使用する必要があります。 その場合は、Skype for Business クライアント KMS キーを確認または追加する必要があります。 KMS を使用していない場合は、Skype for Business クライアント MAK のボリューム ライセンス キーを要求します。
  
## <a name="license-keys"></a>ライセンス キー

Skype Room System は、バックグラウンドで Skype for Business デスクトップ クライアントを実行します。 Skype Room System がドメイン メンバーである場合、KMS が検出されます。 (ボリューム ライセンス KMS キーがある場合は、自動的にアクティブ化されます)。 ボリューム ライセンスには MAK も用意され、xxxxx-xxxxx-xxxxx-xxxxx-xxxxx を表示する場合に入力します。 (MAK を使用してアクティブ化するにはインターネット アクセスが必要ですが、KMS は必要ではありません)。 詳細については、「ボリューム ライセンス認証」を参照Office 2013。
  
- MAK キーを入力するには、[OEM 設定 \> ] SRS ライセンス ツールに移動します。 [状態の確認] をクリックします。 状態が "製品がアクティブ化されていません" と表示された場合は、キーを入力します。
    
- ライセンス認証中に「ソフトウェア ライセンス サービスからプロダクト キーが無効だと報告されました」というエラーが表示される場合は、次の確認を行います。
    
  - キーが正しく入力されました。
    
  - 別のキーではなく、Skype for Business MAK キーを入力しました。
    
  - システムはインターネットにアクセスできます。
    
- 電話でライセンス認証できますが、最初に SRS ライセンス ツールを使用してライセンス認証を試みた必要があります。 電話でアクティブにするには、テスト会議を開始します (短すぎるテスト通話ではありません)。 [ライセンス認証Office] で、[電話のライセンス認証] を選択し、Microsoft に電話し、長い番号を入力して、応答を入力します。
    
## <a name="certificate-authority"></a>証明機関

Web Apps Server 2013 証明書の発行に使用Office証明書失効リスト プロパティに HTTP パスが含まれているか確認します。
  
Skype for Business Server を使用している場合は、証明書ファイル (.crt) を Skype Room System にインポートします。 CA サーバーの CertEnroll 共有、またはドメインに参加している PC の信頼されたルート フォルダーから簡単に取得できます。
  
## <a name="certificates"></a>証明書

証明機関に証明書失効リストの http パスが含されていないことを確認します。 含めない場合は、CA を更新して 1 つを含める。
  
[システム設定証明書マネージャー] の下の Skype Room System の管理者セットアップに証明書を \> インストールします。 内部証明書にはエンタープライズ ルート CA が必要です。
  
必要な証明書を取得する方法の 1 つは、証明書を発行した CA を検出する方法です。 Skype for Business Server の場合は、Skype for Business の PC で、[設定 \> ツール] [ダイヤルイン会議の設定] \> をクリックします。 これにより、内部証明書を発行した CA によってセキュリティで保護された Web ページが開きます。 ブラウザーのアドレス バーの [ロック] アイコンをクリックして、セキュリティ レポートを表示します。 [証明書の表示] をクリックし、CRL 配布ポイント プロパティを確認します。 2 番目の CN パラメーターは、CA のサーバー名である必要があります。 次に、そのアドレス \\ \< CA Server Name \> \CertEnroll の Windows エクスプローラーを開きます。 2 つの .crl ファイルと .crt ファイルをフラッシュ ドライブにコピーし、SMART ボードの左側に置きます。
  
.crt ファイルを信頼できる部屋証明機関フォルダーの下の Skype Room System にインポートします。
  
中間証明書機関フォルダーの下にある Skype Room System の .crl ファイルをインポートします。 (ファイルを表示するには、証明書マネージャーのファイル拡張子フィルターを .crl に変更する必要があります)。
  
注: Office Web Apps 2013 サーバーは、Skype for Business と同じ CA を共有できます。 会議で PowerPoint を共有できない場合。 IT に確認し、上記のように CA ネットワーク共有 CertEnroll から CRT ファイルと CRL ファイルを取得します。 
  
ドメイン メンバーシップは、Skype Room System を Windows システムとして扱い、証明書の側面の一部を Active Directory に依存できるので、いくつかのことを簡略化できます。 ただし、手動で管理する方が最適です。
