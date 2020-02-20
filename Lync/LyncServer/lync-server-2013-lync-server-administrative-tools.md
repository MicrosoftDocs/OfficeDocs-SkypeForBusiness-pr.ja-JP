---
title: 'Lync Server 2013: Lync Server 管理ツール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85ba9b1d9848fa51d798dd93b9cbc53daf69a6b7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a>Lync Server 2013 管理ツール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

このトピックでは、Lync Server 2013 の管理ツールについて説明します。

管理ツールは、各 Lync Server サーバーに既定でインストールされます。 また、専用の管理コンソールなど、他のコンピューター上に管理ツールをインストールすることもできます。 管理ツールをインストールする手順については、「 [Lync Server 2013 管理ツールをインストール](lync-server-2013-install-lync-server-administrative-tools.md)する」を参照してください。 管理タスクを実行するツールを開く手順については、「 [Open Lync Server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

Lync Server 管理ツールをインストールまたは使用する前に、インフラストラクチャ、オペレーティングシステム、ソフトウェア、および管理者の権限要件を確認してください。 インフラストラクチャ要件の詳細については、「 [Lync Server 2013 の管理ツールのインフラストラクチャ要件](lync-server-2013-administrative-tools-infrastructure-requirements.md)」を参照してください。 Lync Server 管理ツールをインストールするためのオペレーティングシステムとソフトウェアの要件の詳細については、「lync server [2013 のサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」、「 [lync server 2013 の追加のソフトウェア要件](lync-server-2013-additional-software-requirements.md)」、および「 [lync server 2013 の追加のサーバーサポートと要件](lync-server-2013-additional-server-support-and-requirements.md)」を参照してください。 ツールをインストールして使用するために必要なユーザー権限とアクセス許可については、「 [Lync Server 2013 のセットアップと管理に必要な管理者権限とアクセス許可](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)」を参照してください。

管理ツールは、次の内容で構成されます。

  - **Lync server 展開ウィザード**   を使用して lync server を展開し、すべての管理ツールをインストールします。

  - **Lync Server トポロジビルダー**   を使用して、展開内のコンポーネントを定義します。

  - **Lync Server コントロールパネル**   web ベースのインターフェイスを使用して、展開の継続的な管理に使用します。

  - **Lync Server 管理シェル**   は、コマンドラインを使用して展開を継続的に管理するために使用します。

  - **Lync Server ログツール**   を使用して、展開の問題のトラブルシューティングを行います。

  - **集中ログサービス**   は、1台のコンピューター、プール、サイト、またはグローバルからログとトレースファイルを収集します。 プロバイダー、フラグ、およびトレースレベルを含むシナリオを選択して定義します。 ログは、テキストベースのツールや Snooper などのツールを使用して収集、集計、表示されます。

トポロジビルダーと Lync Server コントロールパネルを使用して、展開を管理することができます。

<div>

## <a name="deployment-wizard"></a>展開ウィザード

Lync Server をまだインストールしていないコンピューターにすべての管理ツールをインストールするには、インストールメディアに含まれている Lync Server 展開ウィザードを使用する必要があります。 管理ツールのインストールプロセスでは、Lync Server 展開ウィザードが他のツールと共にローカルにインストールされるので、その他のツールを使用して追加のコンポーネントのファイルをインストールしたり、不要なコンポーネントのファイルを削除したりすることができます。コンピューター.

Lync server のインストールメディアから初めて Lync Server 展開ウィザードを実行する方法の詳細については、「 [Install Lync server 2013 管理ツール](lync-server-2013-install-lync-server-administrative-tools.md)」を参照してください。

</div>

<div>

## <a name="topology-builder"></a>トポロジ ビルダー

トポロジビルダーを使用して実行できる展開タスクの詳細については、各サーバーの役割の展開に関するドキュメントを参照してください。

</div>

<div>

## <a name="lync-server-control-panel"></a>Lync Server コントロール パネル

Lync server 2013 コントロールパネルを使用して、Lync Server 2013 の管理と保守に必要な管理タスクの大部分を実行できます。 Lync Server コントロールパネルには、組織内のユーザー、クライアント、およびデバイスに加えて、Lync Server を実行しているサーバーの構成を管理するためのグラフィカルユーザーインターフェイス (GUI) が用意されています。 Lync server 管理シェルは、lync server の構成を実行するための基本的なメカニズムとして Lync Server コントロールパネルを使用します。

Lync server コントロールパネルは、すべての Lync Server フロントエンドサーバーまたは Standard Edition サーバーに自動的にインストールされます。 このリリースでは、ユーザーはエッジ サーバーをリモートで管理します。 Lync server コントロールパネルは、Lync Server を一元管理する管理コンソールなどの別のコンピューターにインストールすることもできます。 詳細については、「 [Install Lync Server 2013 管理ツール](lync-server-2013-install-lync-server-administrative-tools.md)」を参照してください。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server コントロールパネルを使用して設定を構成するには、CsAdministrator の役割に割り当てられているアカウントを使用してログインする必要があります。 Lync Server 2013 で使用できる定義済みの管理者の役割の詳細については、「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync server 2013 で役割ベースのアクセス制御を計画する</A>」を参照してください。</P>
> <LI>
> <P>Lync Server コントロールパネルを使用して設定を構成するには、1024 x 768 の最小画面解像度を持つコンピューターも使用する必要があります。</P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a>Lync Server 管理シェル

Lync Server では、Lync Server 管理シェルによって、管理と管理のための新しい方法が提供されます。 Lync Server 管理シェルは、Windows PowerShell コマンドラインインターフェイスに基づいて構築された強力な管理インターフェイスで、Lync Server に固有の一連のコマンドレットが含まれています。 Lync Server 管理シェルを使用すると、さまざまな構成および自動化の制御セットを入手できます。 トポロジビルダーおよび Lync Server コントロールパネルはいずれも、Lync Server の管理をサポートするために、これらのコマンドレットのサブセットを実装します。 Lync Server 管理シェルには、すべての Lync Server 管理タスク用のコマンドレットが含まれており、コマンドレットを個別に使用して展開を管理できます。 詳細については、「 [Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)のドキュメント」またはコマンドラインヘルプの各コマンドレットを参照してください。

</div>

<div>

## <a name="logging-tool"></a>ログ ツール

Lync Server ログツールは、製品の実行中に、ログとトレース情報を製品からキャプチャすることでトラブルシューティングを容易にします。 このツールを使用して、任意の Lync Server サーバーの役割でデバッグセッションを実行できます。 ログツールの詳細については、TechNet ライブラリの Lync Server 2010 ログツールに関するドキュメント[https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265)を参照してください。

<div>


> [!IMPORTANT]  
> すべての状況で Lync Server ログツール経由のすべてのログ収集に対して、集中ログサービスを使用することをお勧めします。 Lync Server ログツールは引き続き動作しますが、集中ログサービスが既に実行されている場合は、影響を与えるか、ほとんど効果がありません。 集中ログサービスまたは Lync Server ログツールのみを使用する必要がありますが、両方を同時に使用することはできません。 集中ログサービスの詳細と、それを排他的に使用する理由については、「 <A href="lync-server-2013-using-the-centralized-logging-service.md">Lync Server 2013 での集中ログサービスの使用</A>」を参照してください。



</div>

</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 の管理ツールのインフラストラクチャ要件](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Lync Server 2013 でのサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Lync Server 2013 の管理ツールソフトウェア要件](lync-server-2013-administrative-tools-software-requirements.md)

  - [Lync Server 2013 のセットアップと管理に必要な管理者権限およびアクセス許可](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [Lync Server 2013 でトポロジを公開するための要件](lync-server-2013-requirements-to-publish-a-topology.md)

  - [Lync Server 2013 管理ツールのインストール](lync-server-2013-install-lync-server-administrative-tools.md)

  - [Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Lync Server 2013 コントロール パネルのトラブルシューティング](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [Lync Server 2013 での集中ログサービスの使用](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

