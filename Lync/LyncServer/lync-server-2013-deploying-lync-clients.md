---
title: 'Lync Server 2013: Lync クライアントを展開する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bbbecc50ed88ac9b3237277ba1c991f8c1fcba2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a>Lync Server 2013 での Lync クライアントの展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-03_

Lync 2013 では、クライアントの展開にさまざまなアプローチが導入されています。 以前のリリースから出発した Lync 2013 には、独自のインストーラーがありません。 代わりに Lync は、Office 2013 セットアッププログラムに含まれています。 Lync 2013 をユーザーに展開するには、Office 2013 のインストール方法とカスタマイズツールを使用できます。

  - **Office 2013 Windows installer**は、複数の MSI ファイルで構成される windows installer ベースのインストールパッケージです。 言語に依存しないコア MSI パッケージと 1 つ以上の言語固有のパッケージが組み合わされ 1 つの完全な製品になっています。 セットアップによって個々のパッケージがアセンブルされ、ユーザーのコンピューターへの Office のインストール中およびインストール後に、カスタマイズ タスクとメンテナンス タスクが実行されます。 このセクションのトピックでは、Lync 2013 を展開するために Office 2013 Windows インストーラーを使用およびカスタマイズする方法について説明します。

  - **Office 2013 クイック実行**は、office のセットアップファイルを Microsoft office 365 ポータルからユーザーにストリーミングするインストールプログラムです。 管理者は、Office 展開ツールを使用してクイック実行用にインストールをカスタマイズできます。 Office 2013 クイック実行は主に Microsoft Office 365 環境で使用されるため、このインストール方法についてはこのセクションで詳しく説明しません。 クイック実行インストールの使用とカスタマイズの詳細については、「Office 2013 リソースキット」を参照してください。 管理者は、Office 2013 クイック実行プログラムと言語ソースファイルをオンプレミスの場所にダウンロードすることもできます。この機能は、ネットワーク上の需要を最小限に抑えたい場合や、ユーザーがインターネットからソフトウェアをインストールできないようにする場合に便利です。企業のセキュリティ要件。

このセクションのトピックでは、Office 2013 MSI ベースのインストーラーを使用してクライアントを展開する方法について説明します。 主な参照は、Office 2013 リソースキットドキュメントです。ここでは、インフラストラクチャの準備、セットアップのカスタマイズ、Office 2013 の展開の方法について詳しく説明します。 ただし、Office ドキュメントをこのセクションのトピックと組み合わせて使用する必要があります。このセクションでは、Lync 2013 に固有の展開に関する考慮事項について説明します。

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Lync 2013 用のオンライン会議アドインは、Outlook メッセージングおよびコラボレーションクライアント内からの会議管理をサポートしており、Lync 2013 と共に自動的にインストールされます。</P>
> <LI>
> <P>Office 2013 セットアッププログラムでは、以前のバージョンの Lync や Office Communicator はアンインストールされません。 Lync 2013 クライアントは、他の Lync または Office Communicator クライアントと並行してインストールされます。</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 でのクライアントインストールのカスタマイズ](lync-server-2013-customizing-client-installation.md)

  - [Lync Server 2013 での Lync の動作とユーザーインターフェイスのカスタマイズ](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [Lync Server 2013 でのオンライン会議アドインのカスタマイズ](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Lync Server 2013 での会議参加ページの構成](lync-server-2013-configuring-the-meeting-join-page.md)

  - [Lync Server 2013 でサポートされているクライアントバージョンを構成する](lync-server-2013-configuring-supported-client-versions.md)

  - [Lync Server 2013 で拡張プレゼンスプライバシーモードを構成する](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

