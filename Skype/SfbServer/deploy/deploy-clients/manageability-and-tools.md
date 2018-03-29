---
title: Skype Room System の管理容易性とツール
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: このトピックでは、Skype Room System の管理ツールについて説明します。
ms.openlocfilehash: c18c8a1e8f4580551dc809d3a8cedbf6f6a3fbfa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-manageability-and-tools"></a>Skype Room System の管理容易性とツール
 
このトピックでは、Skype Room System の管理ツールについて説明します。
  
## <a name="administrative-portal"></a>管理ポータル

ビジネス サーバー設置型展開では Skype は、積極的に管理し、組織内で Skype ルーム システムの展開を監視する Skype ルーム システムの管理ポータルを使用できます。
  
詳細については、次を参照してください。
  
- [Lync Server 2013 で Lync の部屋のシステム管理用の Web ポータルを展開します。](http://technet.microsoft.com/library/ecba5b36-632e-40b9-9c2e-ab825baf7a46.aspx)
    
- [Lync ルーム システム管理用 Web ポータルの Lync Server 2013 環境を構成します。](http://technet.microsoft.com/library/1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2.aspx)
    
- [Lync Server 2013 で Lync ルーム システム管理用の Web ポータルをインストールします。](http://technet.microsoft.com/library/dd19e368-c338-4e21-a40d-6439d46a9748.aspx)
    
- [Lync ルーム システム管理用の Web ポータルを使用して、Lync Server 2013 で](http://technet.microsoft.com/library/c387b2a3-3e42-4642-af72-88126ed2820f.aspx)
    
## <a name="system-center-operations-manager"></a>System Center Operations Manager

[Skype ルーム システムの管理パック](https://www.microsoft.com/en-us/download/details.aspx?id=42320)をダウンロードし、SCOM サーバー上にインストールすることによって Skype ルームのシステムをシステム センター操作マネージャー (SCOM) を監視できます。 SCOM を使用するアラートを設定する、Skype ルーム システムの稼働状態の監視、稼動状況のレポートなどの作業を生成します。 Skype ルーム システム SCOM サーバーを指すように構成することを事前にインストールされているモニタリング ・ エージェントが付属します。 Skype ルーム システムのモニタリング ・ エージェントを構成する方法を知っている Skype ルーム システムの製造元から提供されたインストール ・ ガイドを参照してください。
  
## <a name="exchange-checklist"></a>Exchange チェックリスト

- 自動検出がセットアップされており、autodiscover.domain.com に対して内部 DNS A/CNAME RECORD が利用可能であることを確認します。
    
- 自動検出の ping を実行します (例: Ping Autodiscover.contoso.com)。
    
- Microsoft 接続アナライザー ツールで自動検出サービスをテストします。 「ログオンできません Office Outlook とします。」最初のテストを選択します。
    
- 会議室には、リソース メールボックスが割り当てられている場合は、Skype ルーム システム (ページの下部にあるスクリプトの例) のアカウントを拡張します。
    
## <a name="skype-for-business-checklist"></a>Skype がビジネス チェックリストについて

- 次のツールを実行します。
    
  - ビジネスのベスト プラクティス アナライザーの Skype 
    
  - Skype のビジネスの稼働状態分析ツール (Excel) 
    
  - 32 ビットまたは 64 ビットの Business Connectivity アナライザーの Skype
    
- [便利な新しいトラブルシューティングと分析ツールを Office 365 で](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/)確認します。 ビジネスのプールと、Office Web Apps サーバーの Skype してビジネスのクライアントは、Skype を使用して PowerPoint デッキを共有することができますを確認します。
    
- 会議室には、リソース メールボックスが割り当てられている場合は、Skype のビジネスに有効にします。
    
- 必要に応じて、会議室システムの DID (電話番号) を要求し、Active Directory ツールで [一般電話] フィールドを更新します。
    
## <a name="network"></a>ネットワーク

- Skype ルーム システムのワイヤード (有線) ネットワーク接続があることを確認します。
    
- ネットワーク ビジネス用の Skype については、ガイドの計画を参照してください。
    
- ビジネス パートナーに、Skype、Skype のビジネス ネットワークの評価を要求します。
    
- ビジネスの稼働状態分析ツール (Excel) の Skype でキャプチャされたパフォーマンス データを参照してください。
    
- ネットワーク分析ツールを実行します。
    
- 通話前診断ツールを実行します。
    
## <a name="skype-room-system-security"></a>Skype ルーム システムのセキュリティ

Skype ルーム システムは、ビジネス ・ セキュリティ ・ モデル、著作権管理、および SCOM などの管理ツールは、Skype を使用して、Windows の展開に完全に統合されている組み込みシステムです。 次の機能が含まれます。
  
- ユーザー モードでのディスクの書き込みを防止する書き込みフィルター 
    
- 許可されていないアプリの実行を防止するアプリ ロッカー。すべての USB ポートがユーザー モードで無効になります。
    
  - 標準的なアプリケーションまたはビューアー上に存在しない Skype ルーム システムのハードウェアです。 すべてのコンテンツは、HTTP プロトコルまたは RDP プロトコル経由で表示されます。
    
  - アプライアンス PC では、Windows Embedded Standard 7 オペレーティング システムを実行します。デバイスを含むすべてのハードウェアは、OEM パートナーによって提供されます。
    
  - Active Directory ドメイン サービス (AD DS) へのオプションのドメイン参加で、ローカル セキュリティ アカウントの管理および制御が可能になります。
    
- ビジネス管理センターは、Skype を使用して、ローカルの管理者アカウントを管理することもできます。
    
- Skype ルーム システムは、標準の Microsoft 更新プログラムのプロセスを通じて更新されます。
    
- Skype ルーム システムは、ビジネスの Skype に接続します。
    
  - ビジネス用の Skype を使用して、エンド ・ ツー ・ エンドの暗号化および認証のすべての通信モード
    
  - Skype ルームのシステムでは、ビジネスのセキュリティとコンプライアンスの標準の Skype をサポートしています。 詳細については、「Lync Server 2013 のセキュリティの計画」を参照してください。
    
## <a name="license"></a>ライセンス

ソフトウェアのライセンス認証に KMS を使用していることを確認します。 場合は、確認するか、Skype のビジネス クライアント KMS キーを追加する必要があります。 KMS を使用していない場合は、ボリューム、Skype のビジネス クライアント MAK のライセンス キーを要求します。
  
## <a name="license-keys"></a>ライセンス キー

Skype ルームのシステムでは、バック グラウンドで、Skype のビジネス デスクトップ クライアントを実行します。 Skype ルーム システムがドメインのメンバーである場合は、KMS を検出します。 (およびボリューム ライセンス KMS Lync キーが自動的にアクティブ化がある場合)。 ボリューム ライセンスは、MAK では、xxxxx xxxxx xxxxx xxxxx が表示されるを入力しても提供します。 (インターネットにアクセスする必要が、MAK、KMS ではないを使用してアクティブにする)。 詳細については、Office 2013 のボリューム ライセンス認証を参照してください。
  
- MAK キーを入力するには、OEM の設定に移動\>SRS ライセンス ツールです。 [状態の確認] をクリックします。 「製品のライセンス認証されていない」と表示されている、キーを入力します。
    
- ライセンス認証中に、エラーが発生した場合は、"' ソフトウェア ライセンス サービス プロダクト キーが有効ではないことを報告される」ことを確認し。
    
  - キーが正しく入力された。
    
  - ビジネス MAK キーと他のキーに、Skype を入力したとします。
    
  - システムにインターネット アクセスがある。
    
- 電話でアクティブにすることができますが、最初に、SRS のライセンス ツールを使用してアクティブにしよう必要があります。 電話でライセンス認証をするには、テスト用会議 (いないテストの呼び出しとしては短すぎる) を起動します。 Office ライセンス認証ウィザードで、電話によるライセンス認証を選択して、マイクロソフト long 型の値を入力し、応答を入力してください。
    
## <a name="certificate-authority"></a>認証局

Office Web Apps Server 2013 の証明書を発行するために使用された認証局で、証明書失効リストのプロパティに HTTP パスが含まれていることを確認します。
  
Skype を使用してビジネスのサーバーの場合は、Skype ルーム システムに証明書ファイル (.crt) をインポートします。 このファイルは、CA サーバーの CertEnroll 共有、またはドメインに参加する任意の PC の Trusted Root フォルダーで、簡単に入手できます。
  
## <a name="certificates"></a>証明書

認証局に証明書失効リストの http パスが含まれることを確認します。このパスが含まれない場合は、CA を更新してパスを含めます。
  
管理システムのセットアップ、Skype ルーム システムの設定] の下で証明書をインストール\>証明書マネージャーです。 内部証明書のエンタープライズ ルート CA が必要です。
  
必要な証明書を取得する方法の 1 つは、証明書を発行した CA を見つけることです。 Skype ビジネス上のサーバー、ビジネス用の Skype で PC 用の [設定] をクリックします\>ツール\>では、ダイヤルイン会議の設定です。 これによって、内部 Lync 証明書を発行した CA によって保護されている Web ページが開きます。 ブラウザーのアドレス バーのロック アイコンをクリックして、セキュリティ レポートを表示します。 [証明書の表示] をクリックし、CRL 配布ポイントのプロパティを調べます。 第 2 の CN パラメーターは、CA のサーバー名であることが必要です。 ここでそのアドレスを Windows エクスプ ローラーを開き\\ \< CA サーバー名\>\CertEnroll。 フラッシュ ドライブに 2 つの .crl ファイルと .crt ファイルをコピーし、SMART ボードの左側に格納します。
  
Skype ルーム システム領域の信頼された証明機関] フォルダーの下に、.crt ファイルをインポートします。
  
中間証明機関] フォルダーの下の Skype ルーム システムの .crl ファイルをインポートします。 (必要な .crl ファイルを表示する証明書マネージャーで [ファイル拡張子のフィルターを変更するのには)。
  
注意: Office Web Apps 2013 サーバーでは、Lync と同じ CA を共有できます。CA を共有していない場合、会議で PowerPoint を共有できません。IT に連絡し、前述したように CA ネットワーク共有 CertEnroll から CRT ファイルおよび CRL ファイルを取得します。 
  
ドメインのメンバーシップは、Windows システムと Skype ・ ルーム ・ システムを扱うことができますし、それに使用できる Active Directory 証明書のさまざまな側面のいくつかあるために、いくつかの点を簡略化できます。 ただし、これは手動で管理することをお勧めします。
  

