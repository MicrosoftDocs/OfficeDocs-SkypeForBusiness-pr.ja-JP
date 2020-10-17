---
title: 'Lync Server 2013: Active Directory スキーマの準備'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27c785596d1fe994e3156eb0e52ed840609a5c26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506854"
---
# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>Lync Server 2013 での Active Directory スキーマの準備

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-08-27_

Active Directory ドメインサービスの準備を開始する前に、Windows メモ帳などのテキストエディターを使用してスキーマファイルを開くか、または lync [server 2013 によって使用される Active directory スキーマ拡張、クラス、属性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) を参照して、lync server 2013 に対して変更されるすべての Active Directory ドメインサービスのスキーマ拡張を確認できます。 Lync Server は、次の4つのスキーマファイルを使用します。

  - ExternalSchema は、Microsoft Exchange Server との相互運用性に使用されます。

  - ServerSchema。これは、プライマリ Lync Server 2013 スキーマファイルです。

  - BackCompatSchema.ldf (以前のリリースのコンポーネントとの相互運用性を確保するために使用されます)

  - VersionSchema.ldf (準備したスキーマのバージョン情報を保持するために使用されます)

以前のリリースから移行しているかどうかや、クリーン インストールを実行しているかどうかに関係なく、すべての .ldf ファイルがスキーマの準備時にインストールされます。 これらのスキーマファイルは、上記の一覧に示されている順序でインストールされ、 \\ \\ インストールメディアの Support スキーマフォルダーにあります。

Lync Server スキーマ拡張機能は、すべてのドメイン間でレプリケートされ、ネットワークトラフィックに影響します。 スキーマの準備は、ネットワークの使用率が低いときに実行してください。

<div>


> [!NOTE]  
> Lync 1.0 モバイルクライアント用の Microsoft® Office Communicator Mobile 2007 R2 および Microsoft® Office Communicator Mobile のサポートを Lync Server 2013 展開に追加する必要がある場合は、Lync Server 2013 のインストール時に Microsoft Office Communications Server 2007 R2 用の Active Directory スキーマを準備する必要があります。 必要なソフトウェアおよびドキュメントについては、「」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A> 。



</div>

<div>

## <a name="adsi-edit"></a>ADSI エディター

Active Directory サービス インターフェイス エディター (ADSI エディター) は AD DS の管理ツールです。これを使用すると、スキーマの準備およびレプリケーションを確認できます。

既定では、AD DS の役割をインストールしてサーバーをドメイン コントローラーにするときに ADSI エディターがインストールされます。 Windows Server 2008 および Windows Server 2008 R2 の場合、ADSI Edit (adsiedit) はリモートサーバー管理ツール (RSAT) に含まれています。 また、RSAT をドメイン メンバー サーバーまたはスタンドアロン サーバーにインストールすることもできます。 RSAT パッケージは、既定で、Windows のインストール時にこれらのサーバーにコピーされますが、インストールされません。 各ツールをインストールするには、サーバー マネージャを使用します。 ADSI エディターは、**[役割管理ツール]**、**[Active Directory ドメイン サービス ツール]**、**[Active Directory ドメイン コントローラー ツール]** を順に展開すると見つかります。

Windows Server 2003 の場合、ADSI エディターはサポート ツールに付属しています。 サポートツールは、サポートツールフォルダーの Windows Server 2003 CD から \\ 入手 \\ するか、「windows Server 2003 Service Pack 2 32-Bit Support tools」からダウンロードでき [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770) ます。 製品 CD からサポートツールをインストールする手順については、「Windows サポートツールをインストールする」を参照して [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771) ください。 サポート ツールをインストールすると、adsiedit.dll が自動的に登録されます。 ただし、ファイルをコンピューターにコピーした場合は、ツールを実行する前に、**regsvr32** コマンドを実行して adsiedit.dll ファイルを登録する必要があります。

</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 での Active Directory スキーマの準備の実行](lync-server-2013-running-schema-preparation.md)

  - [Lync Server 2013 での Active Directory スキーマのレプリケーションの確認](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のフォレストの準備](lync-server-2013-preparing-the-forest.md)  
[Lync Server 2013 のドメインの準備](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

