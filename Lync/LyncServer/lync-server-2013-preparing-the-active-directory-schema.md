---
title: 'Lync Server 2013: Active Directory スキーマの準備'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5479bfbb0774ddd68015de470de082f0cc185b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>Lync Server 2013 での Active Directory スキーマの準備

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-08-27_

Active Directory ドメインサービスの準備を始める前に、Windows メモ帳などのテキストエディターを使用してスキーマファイルを開くか、「 [Active directory スキーマの拡張機能、クラス、および Lync Server 2013 で使用され](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)ているすべてのアクティブな属性を確認する」を参照してください。Lync Server 2013 で変更されるディレクトリドメインサービスのスキーマ拡張機能。 Lync Server では、次の4つのスキーマファイルが使用されます。

  - Microsoft Exchange Server との相互運用性を実現するために使用される ExternalSchema. .ldf

  - ServerSchema: プライマリ Lync Server 2013 スキーマファイル

  - BackCompatSchema。以前のリリースのコンポーネントとの相互運用性を実現するために使用されます。

  - 既成のスキーマのバージョン情報として使用される VersionSchema。

以前のリリースから移行するか、クリーンインストールを実行するかに関係なく、スキーマの準備中にすべての .ldf ファイルがインストールされます。 これらのスキーマファイルは、上に示した順序でインストールされ、インストールメディア\\の\\[サポートスキーマ] フォルダーにあります。

Lync Server スキーマの拡張機能は、ネットワークトラフィックに影響を与えるすべてのドメインにわたってレプリケートされます。 ネットワーク使用量が少なくなったら、一度にスキーマの準備を実行します。

<div>


> [!NOTE]  
> Microsoft® Office Communicator mobile 2007 R2 for Java および Microsoft® Office communicator mobile を使用して 2013 Lync 1.0 モバイルクライアント用のサポートを追加する必要がある場合は、Microsoft Office の Active Directory スキーマを準備する必要があります。Lync Server 2013 のインストール中の Communications Server 2007 R2。 必要なソフトウェアとドキュメントについて<A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>は、を参照してください。



</div>

<div>

## <a name="adsi-edit"></a>ADSI の編集

Active Directory サービスインターフェイスエディター (ADSI Edit) は、スキーマの準備とレプリケーションを確認するために使用できる AD DS 管理ツールです。

サーバーをドメインコントローラーにするには、AD DS の役割をインストールするときに、ADSI の編集が既定でインストールされます。 Windows Server 2008 および Windows Server 2008 R2 の場合、リモートサーバー管理ツール (RSAT) に ADSI Edit (adsiedit) が含まれています。 また、ドメインメンバーサーバーまたはスタンドアロンサーバーに RSAT をインストールすることもできます。 Windows をインストールすると、既定では、RSAT パッケージはこれらのサーバーにコピーされますが、既定ではインストールされません。 サーバーマネージャーを使用して個々のツールをインストールします。 ADSI Edit は、[**役割管理ツール**]、[ **Active Directory ドメインサービスツール**]、[ **active directory ドメインコントローラーツール**] に含まれています。

Windows Server 2003 の場合、ADSI Edit はサポートツールに含まれています。 サポートツールは、Windows Server 2003 CD の [ \\サポート\\ツール] フォルダーにあり[http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770)ます。または、"windows Server 2003 Service Pack 2 32 ビットサポートツール" からダウンロードすることもできます。 製品 CD のサポートツールをインストールする手順については、「Windows サポートツールをインストール[http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771)する」を参照してください。 サポートツールをインストールするときに、Adsiedit が自動的に登録されます。 ただし、ファイルをコンピューターにコピーした場合は、このツールを実行する前に、 **regsvr32**コマンドを実行して、adsiedit ファイルを登録する必要があります。

</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 での Active Directory スキーマの準備の実行](lync-server-2013-running-schema-preparation.md)

  - [Lync Server 2013 での Active Directory スキーマのレプリケーションの確認](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのフォレストの準備](lync-server-2013-preparing-the-forest.md)  
[Lync Server 2013 のドメインの準備](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

