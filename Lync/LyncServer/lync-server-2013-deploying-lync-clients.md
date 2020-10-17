---
title: 'Lync Server 2013: Lync クライアントの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d79eb803b7dd05a7bb03b1189f3a6a4294ec104
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525264"
---
# <a name="deploying-lync-clients-in-lync-server-2013"></a>Lync Server 2013 での Lync クライアントの展開

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-03_

Lync 2013 には、クライアントの展開には別の方法が導入されています。 以前のリリースからの出発では、Lync 2013 には独自のインストーラーがありません。 その代わりに、Lync は Office 2013 セットアッププログラムに含まれています。 Lync 2013 をユーザーに展開するには、Office 2013 のインストール方法とカスタマイズツールを使用できます。

  - **Office 2013 Windows インストーラー** は、複数の MSI ファイルで構成される windows インストーラーベースのインストールパッケージです。 言語に依存しないコア MSI パッケージと 1 つ以上の言語固有のパッケージが組み合わされ 1 つの完全な製品になっています。 セットアップによって個々のパッケージがアセンブルされ、ユーザーのコンピューターへの Office のインストール中およびインストール後に、カスタマイズ タスクとメンテナンス タスクが実行されます。 このセクションのトピックでは、Lync 2013 を展開するために Office 2013 Windows インストーラーを使用およびカスタマイズする方法について説明します。

  - **Office 2013 クイック実行** は、office セットアップファイルを Microsoft 365 管理センターからユーザーにストリームするインストールプログラムです。 管理者は、クイック実行用の Office 展開ツールを使用して、インストールをカスタマイズできます。 Office 2013 クイック実行は、主に Microsoft 365 環境で使用されるため、このセクションではこのインストール方法については詳しく説明しません。 クイック実行インストールの使用およびカスタマイズの詳細については、「Office 2013 リソースキット」のドキュメントを参照してください。 管理者は、Office 2013 クイック実行プログラムおよび言語ソースファイルを社内の場所にダウンロードすることもできます。これは、企業のセキュリティ要件により、ネットワーク上の需要を最小限に抑えたり、ユーザーがインターネットからソフトウェアをインストールしたりできないようにする場合に便利です。

このセクションのトピックでは、Office 2013 MSI ベースのインストーラーを使用してクライアントを展開する方法に重点を置いて説明します。 主な参照は、Office 2013 リソースキットのドキュメントであり、インフラストラクチャの準備、セットアップのカスタマイズ、および Office 2013 の展開方法について詳しく説明されています。 ただし、Lync 2013 に固有の展開に関する考慮事項については、このセクションのトピックと一緒に Office ドキュメントを使用する必要があります。

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Outlook メッセージングおよびコラボレーションクライアント内から会議管理をサポートする Lync 2013 用オンラインミーティングアドインは、Lync 2013 と共に自動的にインストールされます。</P>
> <LI>
> <P>Office 2013 セットアッププログラムを実行しても、以前のバージョンの Lync または Office Communicator はアンインストールされません。 Lync 2013 クライアントは、他の Lync または Office Communicator クライアントと共存してインストールします。</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でのクライアントインストールのカスタマイズ](lync-server-2013-customizing-client-installation.md)

  - [Lync Server 2013 での Lync の動作とユーザーインターフェイスのカスタマイズ](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [Lync Server 2013 でのオンラインミーティングアドインのカスタマイズ](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Lync Server 2013 での会議参加ページの構成](lync-server-2013-configuring-the-meeting-join-page.md)

  - [Lync Server 2013 でサポートされているクライアントバージョンを構成する](lync-server-2013-configuring-supported-client-versions.md)

  - [Lync Server 2013 での拡張プレゼンスプライバシーモードの構成](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

