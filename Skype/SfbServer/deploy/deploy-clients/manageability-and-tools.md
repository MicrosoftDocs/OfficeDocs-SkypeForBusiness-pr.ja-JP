---
title: Skype Room System の管理容易性とツール
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: このトピックでは、Skype Room System の管理ツールについて説明します。
ms.openlocfilehash: 4ae57457eb244e7cf72183bfadba0bd0b89d44a6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293544"
---
# <a name="skype-room-system-manageability-and-tools"></a>Skype Room System の管理容易性とツール
 
このトピックでは、Skype Room System の管理ツールについて説明します。
  
## <a name="administrative-portal"></a>管理ポータル

Skype for Business Server のオンプレミス展開の場合、Skype Room System 管理ポータルを使用して、組織内の Skype Room システムの展開を積極的に管理および監視できます。
  
詳細については、次の記事を参照してください。
  
- [Skype for Business Server で SRS v1 管理 Web ポータルを展開する](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
## <a name="system-center-operations-manager"></a>System Center Operations Manager

Skype Room System [Management Pack](https://www.microsoft.com/download/details.aspx?id=42320)をダウンロードして、scom サーバーにインストールすると、System Center Operations MANAGER (SCOM) を通じて Skype ルームシステムを監視できます。 SCOM を使用して、通知の設定、Skype Room System の正常性の監視、稼働時間レポートの生成などを行うことができます。 Skype Room System には、SCOM サーバを参照するように構成できる事前にインストールされた監視エージェントが付属しています。 Skype room system メーカーから提供されているインストールガイドを参照して、Skype Room システムで監視エージェントを設定する方法を確認してください。
  
## <a name="exchange-checklist"></a>Exchange チェックリスト

- 自動検出がセットアップされており、autodiscover.domain.com に対して内部 DNS A/CNAME RECORD が利用可能であることを確認します。
    
- 自動検出の ping を実行します (例: Ping Autodiscover.contoso.com)。
    
- Microsoft 接続アナライザー ツールで自動検出サービスをテストします。 最初のテストの [Office Outlook でログオンできない] を選択します。
    
- 会議室に既にリソースメールボックスがある場合は、このアカウントを Skype Room System (ページ下部のサンプルスクリプト) に拡張します。
    
## <a name="skype-for-business-checklist"></a>Skype for Business のチェックリスト

- 次のツールを実行します。
    
  - Skype for Business ベストプラクティスアナライザー     
  - Skype for Business の正常性分析ツール (Excel)    
  - Skype for Business Connectivity Analyzer 32 ビットまたは64ビット
    
- [Office 365 用の新しいトラブルシューティングツールと分析ツールを](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/)確認します。 Skype for Business のプールと Office Web Apps サーバーを使用していて、Skype for Business クライアントを使って PowerPoint デッキを共有できることを確認します。
    
- 会議室に既にリソースメールボックスがある場合は、Skype for Business で有効にします。
    
- 必要に応じて、会議室システムの DID (電話番号) を要求し、Active Directory ツールで [一般電話] フィールドを更新します。
    
## <a name="network"></a>ネットワーク

- Skype Room システムの有線ネットワーク接続があることを確認してください。
    
- Skype for Business のネットワーク計画ガイドを参照してください。
    
- Skype for Business パートナーから Skype for Business ネットワークの評価を要求する。
    
- 詳細については、「Skype for Business 正常性分析ツール (Excel) で収集したパフォーマンスデータ」を参照してください。
    
- ネットワーク分析ツールを実行します。
    
- 通話前診断ツールを実行します。
    
## <a name="skype-room-system-security"></a>Skype Room System のセキュリティ

Skype Room System は、Skype for Business のセキュリティモデル、rights management、および SCOM などの管理ツールを使用して、Windows 展開に完全に統合できる埋め込みシステムです。 次の機能が含まれます。
  
- ユーザー モードでのディスクの書き込みを防止する書き込みフィルター 
    
- 許可されていないアプリの実行を防止するアプリ ロッカー。すべての USB ポートがユーザー モードで無効になります。
    
  - Skype Room システムのハードウェアには、標準のアプリやビューアーは存在しません。 すべてのコンテンツは、HTTP プロトコルまたは RDP プロトコル経由で表示されます。
    
  - アプライアンス PC では、Windows Embedded Standard 7 オペレーティング システムを実行します。デバイスを含むすべてのハードウェアは、OEM パートナーによって提供されます。
    
  - Active Directory ドメイン サービス (AD DS) へのオプションのドメイン参加で、ローカル セキュリティ アカウントの管理および制御が可能になります。
    
- また、Skype for Business 管理センターを使って、ローカル管理者アカウントを管理することもできます。
    
- Skype Room System は、Microsoft の標準的な更新プロセスによって更新されます。
    
- Skype Room System は Skype for Business と接続します。
    
  - Skype for Business では、すべての通信モードでエンドツーエンドの暗号化と承認が使用されます。
    
  - Skype Room System は、Skype for Business のセキュリティとコンプライアンス標準をサポートしています。 詳細については、「 [Skype For Business Server のセキュリティの計画](../../plan-your-deployment/security/security.md)」を参照してください。
    
## <a name="license"></a>ライセンス

ソフトウェアのライセンス認証に KMS を使用していることを確認します。 その場合は、Skype for Business クライアントの KMS キーを確認または追加する必要があります。 KMS を使用していない場合は、Skype for Business クライアント MAK のボリュームライセンスキーを要求します。
  
## <a name="license-keys"></a>ライセンス キー

Skype Room System は、バックグラウンドで Skype for Business デスクトップクライアントを実行します。 Skype Room System がドメインメンバーである場合は、KMS が検出されます。 (また、ボリュームライセンスの KMS キーが含まれている場合は、ライセンス認証が自動的に有効になります)。 ボリュームライセンスにも MAK が用意されています。この場合、「xxxxx」と入力します。 (ライセンス認証を行うには、インターネットに接続している必要があります)。 詳細については、「Office 2013 のボリュームライセンス認証」を参照してください。
  
- MAK キーを入力するには、OEM 設定\>の SRS ライセンスツールに移動します。 [状態の確認] をクリックします。 状態に "製品はライセンス認証されていません" と表示される場合は、キーを入力します。
    
- ライセンス認証中に "" というエラーメッセージが表示される場合は、「ソフトウェアライセンスサービスでプロダクトキーが無効であることが報告されました」というエラーが表示されます。次のことを確認します。
    
  - キーが正しく入力された。
    
  - Skype for Business MAK キーを入力したが、別のキーではありませんでした。
    
  - システムにインターネット アクセスがある。
    
- 電話でライセンス認証することはできますが、最初に SRS ライセンスツールを使用してライセンス認証を行おうとする必要があります。 電話でライセンス認証するには、テスト会議を開始します (これは短いため、テスト通話ではありません)。 Office ライセンス認証ウィザードで、[電話でのライセンス認証] を選択し、[Microsoft に電話をかける] を選びます。長い番号を入力して、返信を入力します。
    
## <a name="certificate-authority"></a>認証局

Office Web Apps Server 2013 の証明書を発行するために使用された認証局で、証明書失効リストのプロパティに HTTP パスが含まれていることを確認します。
  
Skype for Business Server を使用している場合は、証明書ファイル (.crt) を Skype Room System にインポートします。 このファイルは、CA サーバーの CertEnroll 共有、またはドメインに参加する任意の PC の Trusted Root フォルダーで、簡単に入手できます。
  
## <a name="certificates"></a>証明書

認証局に証明書失効リストの http パスが含まれることを確認します。このパスが含まれない場合は、CA を更新してパスを含めます。
  
システム設定\>証明書マネージャーの下にある Skype Room システムの管理セットアップで、証明書をインストールします。 内部証明書のエンタープライズ ルート CA が必要です。
  
必要な証明書を取得する方法の 1 つは、証明書を発行した CA を見つけることです。 Skype for business Server の場合は、Skype for Business の PC で、[ \>設定\>ツール] の [ダイヤルイン会議の設定] をクリックします。 これにより、内部証明書を発行した CA によって保護された web ページが開きます。 ブラウザーのアドレス バーのロック アイコンをクリックして、セキュリティ レポートを表示します。 [証明書の表示] をクリックし、CRL 配布ポイントのプロパティを調べます。 第 2 の CN パラメーターは、CA のサーバー名であることが必要です。 次に、そのアドレス\\ \< CA サーバー名\>\CertEnroll. の Windows エクスプローラーを開きます。 フラッシュ ドライブに 2 つの .crl ファイルと .crt ファイルをコピーし、SMART ボードの左側に格納します。
  
.Crt ファイルを、[Trusted Room サーティフィケーション Authority] フォルダーの下にある Skype Room System にインポートします。
  
[中間証明機関] フォルダーの下にある Skype Room システムに .crl ファイルをインポートします。 (ファイルを表示するには、証明書マネージャーの [ファイル拡張子] フィルターを [crl] に変更する必要があります)。
  
注: Office Web Apps 2013 サーバーは、Skype for Business と同じ CA を共有している可能性があります。 CA を共有していない場合、会議で PowerPoint を共有できません。 IT に連絡し、前述したように CA ネットワーク共有 CertEnroll から CRT ファイルおよび CRL ファイルを取得します。 
  
Skype Room System を Windows システムとして扱うことができるため、証明書の一部については Active Directory に依存していることがあります。 ただし、これは手動で管理することをお勧めします。
  

