---
title: 'Lync Server 2013: サーバーおよびアプリケーションの強化と保護'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42b8b9d3fc21c590bda12841cb6002987d4c0650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a>Lync Server 2013 のサーバーおよびアプリケーションの強化と保護

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-12-05_

特定のコンポーネントのベストプラクティスに従って、オペレーティングシステムとアプリケーションを強化して保護する必要があります。 このセクションでは、アプリケーションサーバーを強化する方法と、グループポリシーを使ってセキュリティ lockdowns を実装する方法について説明します。

<div>


> [!NOTE]  
> Microsoft Lync Server 2013 の展開に使用されるデータベースを強化および保護することもできます。 詳細については、「 <A href="lync-server-2013-hardening-and-protecting-databases.md">Lync Server 2013 のデータベースの強化と保護</A>」を参照してください。



</div>

<div>

## <a name="securing-application-servers"></a>アプリケーションサーバーをセキュリティで保護する

アプリケーションサーバーの場合、オペレーティングシステムとアプリケーションが強化されている必要があります。 たとえば、Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバー2006の実行専用の Windows Server 2008 コンピューターは、オペレーティングシステムとアプリケーションの観点から強化する必要があります。 サーバーによって実行されるサービスの数を最小限に抑えることは、主な目標です。

</div>

<div>

## <a name="securing-virtual-servers"></a>仮想サーバーをセキュリティで保護する

仮想サーバースナップショットには、サーバーのデータディスクのコピーと、メモリ内データのダンプも含まれています。どちらの場合も、攻撃を招く可能性のある機密性の高い暗号化データが含まれている可能性があります。 仮想化を使用して実装された運用サーバーの場合は、サーバースナップショットをすべて無効にするか、非常に制御された方法で管理する必要があります。 Hyper-v 仮想サーバーのセキュリティ保護の詳細については、「」の Hyper-v セキュリティガイド[http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176)を参照してください。

</div>

<div>

## <a name="group-policy"></a>グループポリシー

Windows Server 2008 および Windows Server 2008 R2 では、グループポリシーによってディレクトリベースのデスクトップ構成管理が提供されます。 グループポリシーを使用して、次のようにコンピューターとユーザーの設定をグループポリシーオブジェクト (GPO) 内で定義することにより、セキュリティ lockdowns を実装できます。

  - レジストリベースのポリシー

  - セキュリティ

  - ソフトウェアのインストール

  - スクリプト

  - フォルダリダイレクション

  - リモートインストールサービス

これらの設定を構成する管理者向けのユーザーインターフェイスを提供するために、管理用テンプレートは、オペレーティングシステムリリース、service pack リリース、および Lync Server 2013 などの一部のアプリケーションに付属しています。

Communicator ファイルは、Lync Server 2013 に付属している管理用テンプレートであり、% windir%\\inf\\ディレクトリにインストールされ、グループポリシー設定のインターフェイスを提供します。 Communicator の各設定は、アプリケーションの動作に影響するレジストリ内の設定に対応しています。

設定は、Active Directory ユーザーとコンピューター本体およびグループポリシー管理コンソール (GPMC) から利用できる GPedit からアクセスできます。

</div>

<div>

## <a name="group-policy-security-settings"></a>グループポリシーのセキュリティ設定

グループポリシーには、GPedit からアクセスした場合の、[コンピューターの構成]、[Windows の設定]、[セキュリティ設定] の下にある GPO のセキュリティ設定が含まれています。 セキュリティテンプレートをインポートして、GPO のセキュリティ設定を構成することができます。 Windows server 2008 セキュリティガイド[http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186)と windows Server 2008 R2 セキュリティコンプライアンス管理ツールキットに[http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882)は、必要に応じて変更できる多数のサンプルテンプレートが含まれています。

</div>

<div>

## <a name="best-practices"></a>ベスト プラクティス

  - すべてのサーバーオペレーティングシステムとアプリケーションを強化します。

  - サーバーのスナップショットを保護し、すべての仮想サーバーのセキュリティを強化します。

  - グループポリシーを使用して、セキュリティ lockdowns を実装します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

