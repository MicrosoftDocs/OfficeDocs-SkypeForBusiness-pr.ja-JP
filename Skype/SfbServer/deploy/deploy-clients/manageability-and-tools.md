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
description: このトピックでは、Skype Room System の管理ツールについて説明します。
ms.openlocfilehash: f46d636bba0779cc42532cc2110ef94abdb6b982
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805797"
---
# <a name="skype-room-system-manageability-and-tools"></a>Skype Room System の管理性とツール
 
このトピックでは、Skype Room System の管理ツールについて説明します。
  
## <a name="administrative-portal"></a>管理ポータル

Skype for Business Server のオンプレミス展開では、Skype Room System 管理ポータルを使用して、組織内の Skype Room System の展開を積極的に管理および監視できます。
  
詳細については、次の記事を参照してください。
  
- [Skype for Business Server での SRS v1 管理 Web ポータルの展開](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Exchange チェックリスト

- 自動検出が設定され、内部 DNS A/CNAME RECORD が自動検出で使用autodiscover.domain.com。
    
- Ping 自動検出 (例: Ping Autodiscover.contoso.com)。
    
- Microsoft Connectivity Analyzer ツールを使用して自動検出サービスをテストします。 最初のテスト「Outlook でログオンできない」をOfficeします。
    
- 会議室に既にリソース メールボックスがある場合は、このアカウントを Skype Room System 用に拡張します (ページの下部にあるスクリプトの例)。
    
## <a name="skype-for-business-checklist"></a>Skype for Business チェックリスト

- 次のツールを実行します。
    
  - Skype for Business ベスト プラクティス アナライザー     
  - Skype for Business Health Analysis Tool (Excel)    
  - Skype for Business Connectivity Analyzer 32 ビットまたは 64 ビット
    
- Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/). Skype for Business プールと Office Web Apps サーバーを使用し、Skype for Business クライアントを使用して PowerPoint デッキを共有できます。
    
- 会議室に既にリソース メールボックスがある場合は、Skype for Business で有効にします。
    
- 必要に応じて、会議室システムの DID (電話番号) を要求し、Active Directory ツールの [全般電話] フィールドを更新します。
    
## <a name="network"></a>ネットワーク

- Skype Room System のワイヤード (有線) ネットワーク接続を使用してください。
    
- Skype for Business のネットワーク計画ガイドをお読みください。
    
- Skype for Business パートナーに Skype for Business ネットワーク評価を要求します。
    
- Skype for Business Health Analysis Tool (Excel) でキャプチャされたパフォーマンス データを読み取ります。
    
- ネットワーク分析ツールを実行します。
    
- 通話前診断ツールを実行します。
    
## <a name="skype-room-system-security"></a>Skype Room System のセキュリティ

Skype Room System は、Skype for Business セキュリティ モデル、権限管理、SCOM などの管理ツールを使用して、Windows 展開に完全に統合できる埋め込みシステムです。 以下の機能があります。
  
- ユーザー モードでのディスク書き込みを防止する書き込みフィルター 
    
- 承認されていないアプリが実行されるのを防ぐためのアプリ の防止機能です。 ユーザー モードでは、すべての USB ポートが無効になります。
    
  - 標準のアプリやビューアーは Skype Room System ハードウェアに存在しはありません。 すべてのコンテンツは、HTTP プロトコルまたは RDP プロトコルを介してレンダリングされます。
    
  - アプライアンス PC は、Windows Embedded Standard 7 オペレーティング システムを実行します。 デバイスを含むすべてのハードウェアは、OEM パートナーによって提供されます。
    
  - オプションの Active Directory ドメイン サービス (AD DS) へのドメイン参加により、ローカル セキュリティ アカウントの管理と制御が可能になります。
    
- Skype for Business 管理センターを使用してローカル管理者アカウントを管理することもできます。
    
- Skype Room System は、標準の Microsoft Update プロセスによって更新されます。
    
- Skype Room System は Skype for Business に接続します。
    
  - Skype for Business では、すべての通信モードでエンドツーエンドの暗号化と承認を使用します。
    
  - Skype Room System は、Skype for Business のセキュリティとコンプライアンスの標準をサポートしています。 詳細 [については、「Skype For Business Server のセキュリティを計画する](../../plan-your-deployment/security/security.md) 」を参照してください。
    
## <a name="license"></a>ライセンス

ソフトウェアのライセンス認証に KMS を使用する必要があります。 その場合は、Skype for Business クライアント KMS キーを確認または追加する必要があります。 KMS を使用していない場合は、Skype for Business クライアント MAK のボリューム ライセンス キーを要求します。
  
## <a name="license-keys"></a>ライセンス キー

Skype Room System は、バックグラウンドで Skype for Business デスクトップ クライアントを実行します。 Skype Room System がドメイン メンバーである場合は、KMS を検出します。 (ボリューム ライセンス KMS キーがある場合は、自動的にライセンス認証されます)。 ボリューム ライセンスでは MAK も提供されます。MAK は、xxxxx-xxxxx-xxxxx-xxxxx-xxxxx を表示する場合に入力します。 (MAK を使ってライセンス認証するにはインターネット アクセスが必要ですが、KMS は必要ではありません)。 詳細については、「ボリューム ライセンス認証」を参照Office 2013。
  
- MAK キーを入力するには、OEM 設定 \> SRS ライセンス ツールに移動します。 [状態の確認] をクリックします。 状態が "製品がアクティブ化されていません" と表示された場合は、キーを入力します。
    
- ライセンス認証中に、「ソフトウェア ライセンス サービスがプロダクト キーが無効だと報告しました」というエラーが表示された場合は、次の確認を行います。
    
  - キーが正しく入力されました。
    
  - 別のキーではなく、Skype for Business MAK キーを入力しました。
    
  - システムはインターネットにアクセスできます。
    
- 電話でライセンス認証できますが、最初に SRS ライセンス ツールを使用してライセンス認証を試みた必要があります。 電話でライセンス認証を行う場合は、テスト会議を開始します (テスト通話は短すぎます)。 ライセンス認証Officeウィザードで、電話によるライセンス認証を選択し、Microsoft に電話して、長い番号を入力して、応答を入力します。
    
## <a name="certificate-authority"></a>証明機関

Web Apps サーバー 2013 証明書の発行Office証明書失効リスト プロパティに HTTP パスが含まれているか確認します。
  
Skype for Business Server を使用している場合は、証明書ファイル (.crt) を Skype Room System にインポートします。 これは、CA サーバーの CertEnroll 共有、またはドメインに参加している PC の信頼されたルート フォルダーから簡単に取得できます。
  
## <a name="certificates"></a>証明書

証明機関が証明書失効リストの http パスを持っているのを確認します。 含めない場合は、CA を更新して含める必要があります。
  
Skype Room System の管理者セットアップで、システム設定証明書マネージャーの下に証明書を \> インストールします。 内部証明書にはエンタープライズ ルート CA が必要です。
  
必要な証明書を取得する方法の 1 つは、証明書を発行した CA を検出する方法です。 Skype for Business Server の場合は、Skype for Business の PC で、[設定ツール] の [ダイヤルイン会議の設定] \> \> をクリックします。 これにより、内部証明書を発行した CA によってセキュリティ保護された Web ページが開きます。 ブラウザーのアドレス バーの [ロック] アイコンをクリックして、セキュリティ レポートを表示します。 [証明書の表示] をクリックし、CRL 配布ポイントのプロパティを確認します。 2 番目の CN パラメーターは、CA のサーバー名である必要があります。 ここで、そのアドレス \\ \< CA Server Name \> \CertEnroll のエクスプローラーを開きます。 2 つの .crl ファイルと .crt ファイルをフラッシュ ドライブにコピーし、SMART ボードの左側に置きます。
  
.crt ファイルを、Trusted Room Certification Authority フォルダーの下の Skype Room System にインポートします。
  
.crl ファイルを Skype Room System の中級証明書機関フォルダーにインポートします。 (ファイルを表示するには、証明書マネージャーのファイル拡張子フィルターを .crl に変更する必要があります)。
  
注: Office Web Apps 2013 サーバーは、Skype for Business と同じ CA を共有する場合があります。 共有しない場合は、会議で PowerPoint を共有できます。 IT に確認し、上記のように CA ネットワーク共有 CertEnroll から CRT ファイルと CRL ファイルを取得します。 
  
ドメイン メンバーシップは、Skype Room System を Windows システムとして扱い、証明書の側面の一部を Active Directory に依存できる点から、一部の作業を簡素化できます。 ただし、手動で管理する方が最適です。
  

