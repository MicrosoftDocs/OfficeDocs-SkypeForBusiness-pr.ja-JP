---
title: 'Lync Server 2013: 追加サーバー サポートおよび要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29f2d1a1b728fcec84f0aed70f00f1143c70c490
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a>Lync Server 2013 の追加サーバー サポートおよび要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-12-09_

このサポート文書の他のセクションで説明されているソフトウェアのサポートに加えて、Lync Server 2013 には次のサポート制限があります。

  - Lync Server 2013 は、特定のサーバーの役割に対して、ドメインネームシステム (DNS) とハードウェアの負荷分散をサポートしています。 また、必要に応じて、仲介サーバーのアプリケーションロードバランシングもサポートしています。 それぞれの用途の詳細については、計画に関するドキュメントをご覧ください。

  - Lync Server 2013 は、配布リスト展開プロトコル (DLX) を使用して配布リストを展開します。 このプロトコルは、配布リストのメンバーシップを取得するために使用される web サービスメソッドも指定します。 Microsoft Exchange Server では、メンバーに静的に割り当てられていない動的なグループがサポートされています。 代わりに、グループを展開したときに評価されるクエリを保存します。 DLX は動的配布リストをサポートしていません。 この DLX の制限は、すべてのバージョンの Lync Server に適用されます。

  - [ユーザーの有効化] ウィザードでは、英語以外の文字の SIP 準拠の URI への自動変換はサポートされていないため、SIP アドレスを手動で変更する必要があります。

  - ウイルス対策ソフトウェアを実行しているサーバーの場合は、「 [Lync Server 2013 のウイルススキャン除外](lync-server-2013-antivirus-scanning-exclusions.md)」を参照して、ウイルスの除外やその他のセキュリティ関連の推奨事項を参照してください。

  - IPsec を使用している場合は、音声とビデオのトラフィックに使われるポート範囲で IPsec を無効にすることをお勧めします。 詳細については、計画ドキュメントの「 [Lync Server 2013 での IPsec の例外](lync-server-2013-ipsec-exceptions.md)」を参照してください。

  - 組織でサービスの品質 (QoS) インフラストラクチャが使用されている場合、メディア サブシステムは、この既存のインフラストラクチャで機能するように設計されています。 QoS の実装について詳しくは、「運用ドキュメントの[Lync Server 2013 でのサービスの品質 (QoS) の管理](lync-server-2013-managing-quality-of-service-qos.md)」をご覧ください。

  - オペレーティングシステムファイアウォールの使用はサポートされています。 Lync Server 2013 は、Microsoft SQL Server データベースソフトウェアを除き、オペレーティングシステムファイアウォールのファイアウォール例外を管理します。 SQL Server のファイアウォール要件の詳細については、SQL Server のドキュメントを参照してください。

  - 外部ユーザーアクセスのサポートを実装するために使用される外部インターフェイスは、内部インターフェイスと同じネットワーク上では*なく*、別のサブネット上にある必要があります。

  - Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。

  - Lync server 2013 累積更新プログラムのリリースでは、2013年7月、Lync Server 2013 で2段階認証がサポートされるようになりました。 詳細については、「 [Lync Server 2013 での2要素認証](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md)」を参照してください。

  - ほとんどの内部サーバーでは、**オープン認証**(OAuth) として定義された証明書の種類が必要です。 要求時に OAuth 証明書を要求して割り当てる必要があります。 Lync Server 展開ウィザードの [**証明書のインストールと割り当て]** フェーズを行う必要があります。 OAuth 証明書キーの最小サイズは、1024ビットです。 長さが2048ビット未満のキーの長さを持つ証明書を要求した場合は、警告が表示されることがあります。 警告の代わりに2048のキーの長さが強制された場合に発生する可能性のある問題を回避するために、OAuth 証明書のキーの長さとして常に2048を使うことを強くお勧めします。

  - Lync Server 2013 および Microsoft Exchange Server 2010 Service Pack 1 (SP1) では、Windows Server 2008 R2 オペレーティングシステムが、FIPS 140-2 アルゴリズムを使用するように構成されている場合に、米国連邦情報処理標準 (FIPS) 140-2 アルゴリズムのサポートを利用して動作します。システム暗号化。 FIPS サポートを実装するには、Lync Server 2013 を実行している各サーバーでサポートされるように構成する必要があります。 FIPS 準拠のアルゴリズム、および FIPS サポートを実装する方法の詳細については、Microsoft サポート技術情報の記事811833「システム暗号化: Windows XP 以降の暗号化、ハッシュ、署名のセキュリティ設定で FIPS に準拠したアルゴリズムを使用する」を参照してください。Windows のバージョン[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)。 Exchange 2010 の FIPS 140-2 のサポートと制限事項の詳細については、「Exchange 2010 SP1 と FIPS 準拠アルゴリズム[http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)のサポート」を参照してください。

Lync Server 2013 では、展開前または展開中に、特定のコンポーネントにその他のソフトウェアをインストールする必要があります。 これには、オペレーティングシステム、ダウンロード可能なソフトウェア、および Lync Server 2013 のインストール時に自動的にインストールされるソフトウェアで利用できるソフトウェアが含まれます。 必要に応じて、その他のソフトウェアの一覧を次に示します。

  - Windows Update

  - Windows Identity Foundation

  - Microsoft .NET 4.5 フレームワーク

  - Microsoft Visual C++ 2012 再頒布可能
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 をインストールすると、Microsoft Visual C++ 2012 再頒布可能パッケージが自動的にインストールされます。 他のバージョンをインストールして使用することはできません。

    
    </div>

  - URL リライトモジュールバージョン2.0 の再頒布可能

  - Windows Media フォーマット ランタイム

  - Windows PowerShell バージョン3.0

  - Microsoft Silverlight 4 browser プラグイン (Silverlight 4.0.50524.0 または Lync Server コントロールパネルの最新バージョン)

  - Active Directory ドメインサービスツール

これらのソフトウェア要件の一部は、特定のサーバーの役割またはコンポーネントにのみ適用されます。 これらのソフトウェア要件の詳細については、計画ドキュメントの「 [Lync Server 2013 のその他のソフトウェア要件](lync-server-2013-additional-software-requirements.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

