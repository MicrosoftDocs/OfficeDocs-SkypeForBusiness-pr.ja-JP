---
title: 'Lync Server 2013: その他のサーバーのサポートと要件'
description: 'Lync Server 2013: サーバーのサポートと要件が追加されています。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3af9b3489ba62b3b2dc7cf4fa16cabfe80003e1e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542333"
---
# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a>Lync Server 2013 におけるその他のサーバーのサポートおよび要件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-12-09_

このサポートドキュメントの他のセクションで説明されているソフトウェアサポートに加えて、Lync Server 2013 には次のサポート制限があります。

  - Lync Server 2013 では、特定のサーバーの役割に対してドメインネームシステム (DNS) とハードウェア負荷分散がサポートされています。 また、仲介サーバーのアプリケーション負荷分散も、必要に応じてサポートします。 それぞれをいつ使用するかの詳細については、「計画」のドキュメントを参照してください。

  - Lync Server 2013 は、配布リスト展開プロトコル (DLX) を使用して、配布リストを展開します。 このプロトコルは、配布リストのメンバーシップの取得に使用する Web サービス メソッドも指定します。 Microsoft Exchange Server は、静的に割り当てられたメンバーを持たない動的グループをサポートしています。 代わりにこれらのグループは、グループの展開時に評価されるクエリを格納します。 DLX は動的な配布リストをサポートしていません。 この DLX の制限は、Lync Server のすべてのバージョンに適用されます。

  - ユーザーの有効化ウィザードでは、英語以外の文字の SIP 準拠 URI への自動変換はサポートされていません。したがって、SIP アドレスを手動で変更する必要があります。

  - ウイルス対策ソフトウェアを実行しているサーバーについては、「 [Lync Server 2013 のウイルス対策スキャン除外](lync-server-2013-antivirus-scanning-exclusions.md) 」を参照してください。ウイルスの推奨候補およびその他のセキュリティ関連の推奨事項

  - IPsec を使用する場合は、音声およびビデオ トラフィックに使用されるポート範囲に対する IPsec を無効にすることをお勧めします。 詳細については、「計画」のドキュメントの「 [IPsec 例外 (Lync Server 2013](lync-server-2013-ipsec-exceptions.md) )」を参照してください。

  - 組織でサービスの品質 (QoS) インフラストラクチャが使用されている場合、メディア サブシステムは、この既存のインフラストラクチャで機能するように設計されています。 QoS の実装の詳細については、「操作」のドキュメントの「 [Lync Server 2013 でのサービスの品質 (qos) の管理](lync-server-2013-managing-quality-of-service-qos.md) 」を参照してください。

  - オペレーティング システムのファイアウォールの使用がサポートされています。 Lync Server 2013 は、Microsoft SQL Server データベースソフトウェアを除き、オペレーティングシステムファイアウォールのファイアウォール例外を管理します。 SQL Server のファイアウォールの要件の詳細については、SQL Server のドキュメントを参照してください。

  - 外部ユーザー アクセスのサポートの実装で使用する外部インターフェイスは、内部インターフェイスと同じネットワーク上*ではなく*、別のサブネット上にある必要があります。

  - Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。

  - Lync Server 2013 の累積的な更新プログラム (2013 年7月) のリリースでは、Lync Server 2013 は2要素認証をサポートするようになりました。 詳細については、「 [Lync Server 2013 の2要素認証](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md)」を参照してください。

  - ほとんどの内部サーバーでは、証明書の種類として **[オープン認証** (OAuth)] と定義されている必要があります。 [Lync Server 展開ウィザード] の [ **証明書の要求、インストール、および割り当て** ] フェーズで OAuth 証明書を要求して割り当てる必要があります。 OAuth 証明書キーの最小サイズは1024ビットです。 キーの長さが2048ビット未満の証明書を要求した場合は、警告が表示されることがあります。 警告の代わりに2048のキー長が適用された場合に発生する可能性のある問題を回避するために、OAuth 証明書には常に2048のキー長を使用することを強くお勧めします。

  - Lync Server 2013 と Microsoft Exchange Server 2010 Service Pack 1 (SP1) は、Windows Server 2008 R2 オペレーティングシステムがシステム暗号化に FIPS の140-2 アルゴリズムを使用するように構成されている場合に、連邦情報処理規格 (FIPS) の140-2 アルゴリズムをサポートするように動作します。 FIPS サポートを実装するには、Lync Server 2013 を実行している各サーバーをサポートするように構成する必要があります。 FIPS 準拠アルゴリズムと FIPS サポートを実装する方法の詳細については、Microsoft サポート技術情報の記事811833「システム暗号化: Windows XP およびそれ以降のバージョンの Windows で暗号化、ハッシュ、署名のセキュリティ設定を使用する」を参照してください [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833) 。 Exchange 2010 の FIPS 140-2 のサポートおよび制限事項の詳細については、「Exchange 2010 SP1 およびサポートされている FIPS 準拠アルゴリズムのサポート」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335) 。

Lync Server 2013 では、展開前または展開中に特定のコンポーネントに他のソフトウェアをインストールする必要があります。 これには、オペレーティングシステム、ダウンロード可能なソフトウェア、および Lync Server 2013 のインストール時に自動的にインストールされるソフトウェアで利用できるソフトウェアが含まれています。 必要になる可能性のある追加ソフトウェアは、次の一覧のとおりです。

  - Windows Update

  - Windows Identity Foundation

  - Microsoft .NET 4.5 Framework

  - Microsoft Visual C++ 2012 再頒布可能パッケージ
    
    <div>
    

    > [!NOTE]  
    > Microsoft Visual C++ 2012 再頒布可能パッケージは、Lync Server 2013 をインストールすると、自動的にインストールされます。 他のバージョンをインストールして使用することはできません。

    
    </div>

  - URL Rewrite Module Version 2.0 (再頒布可能)

  - Windows Media フォーマット ランタイム

  - Windows PowerShell バージョン3.0

  - Microsoft Silverlight 4 ブラウザー プラグイン (Lync Server コントロール パネルの場合は Silverlight 4.0.50524.0 または最新バージョン)

  - Active Directory ドメインサービスのツール

上記のソフトウェア要件の中には、特定のサーバーの役割またはコンポーネントに対してのみ適用されるものもあります。 これらのソフトウェア要件の詳細については、「計画」のドキュメントの「 [Lync Server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md) 」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

