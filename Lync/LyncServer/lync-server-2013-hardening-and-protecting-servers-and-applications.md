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
ms.openlocfilehash: 6b0a6179e77e4688693fe277748a8933a9dbe911
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a>Lync Server 2013 のサーバーおよびアプリケーションの強化と保護

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-12-05_

個々のコンポーネントのベスト プラクティスに従って、オペレーティング システムおよびアプリケーションを強化して保護することをお勧めします。 ここでは、アプリケーション サーバーを強化し、グループ ポリシーを使用してセキュリティ ロックダウンを実装する方法を説明します。

<div>


> [!NOTE]  
> Microsoft Lync Server 2013 の展開に使用するデータベースを強化および保護することもできます。 詳細については、「 <A href="lync-server-2013-hardening-and-protecting-databases.md">Lync Server 2013 のデータベースのセキュリティ強化と保護</A>」を参照してください。



</div>

<div>

## <a name="securing-application-servers"></a>アプリケーション サーバーのセキュリティ保護

アプリケーション サーバーの場合は、オペレーティング システムとアプリケーションを強化する必要があります。たとえば、Microsoft Internet Security and Acceleration (ISA) Server 2006 の実行専用に使用する Windows Server 2008 コンピューターは、オペレーティング システムとアプリケーションの両方の面から強化する必要があります。主な目標は、サーバーで実行および提供されるサービスの数をできるだけ少なくすることです。

</div>

<div>

## <a name="securing-virtual-servers"></a>仮想サーバーのセキュリティ保護

仮想サーバーのスナップショットには、サーバーのデータディスクのコピーが含まれており、メモリ内データのダンプも含まれています。どちらにも、攻撃につながる可能性がある機密性の高い暗号化データを含めることができます。 仮想化を使用して実装された運用サーバーでは、すべてのサーバーのスナップショットを無効にするか、非常に制御された方法で管理する必要があります。 Hyper-v 仮想サーバーのセキュリティ保護の詳細については、「」の「Hyper-v Security [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176)Guide」を参照してください。

</div>

<div>

## <a name="group-policy"></a>グループ ポリシー

Windows Server 2008 および Windows Server 2008 R2 では、グループ ポリシーにより、ディレクトリ ベースのデスクトップ構成の管理が行われます。次のグループ ポリシー オブジェクト (GPO) 内でコンピューターとユーザーの設定を定義することにより、グループ ポリシーを使用してセキュリティ ロックダウンを実装できます。

  - レジストリ ベースのポリシー

  - セキュリティ

  - ソフトウェアのインストール

  - スクリプト

  - フォルダー リダイレクト

  - リモート インストール サービス

管理者がこれらの設定を構成するためのユーザーインターフェイスを提供するために、管理用テンプレートにはオペレーティングシステムのリリース、service pack のリリース、および Lync Server 2013 を含む一部のアプリケーションが付属しています。

Communicator ファイルは、Lync Server 2013 に付属している管理用テンプレートで、% windir%\\inf\\ディレクトリにインストールされ、グループポリシー設定へのインターフェイスを提供します。 Communicator.adm の各設定は、アプリケーションの動作に影響するレジストリの設定に対応しています。

この設定には、GPedit.dll からアクセスできます。GPedit.dll は、Active Directory ユーザーとコンピューターのコンソールおよびグループ ポリシー管理コンソール (GPMC) から利用できます。

</div>

<div>

## <a name="group-policy-security-settings"></a>グループ ポリシーのセキュリティの設定

グループポリシーには、GPedit からアクセスする場合の [コンピューターの構成]、[Windows の設定]、[セキュリティの設定] にある GPO のセキュリティ設定が含まれています。 セキュリティテンプレートをインポートして、GPO のセキュリティ設定を構成することができます。 「Windows Server 2008 セキュリティガイド」 [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186)および「windows Server 2008 R2 セキュリティコンプライアンス管理ツールキット[http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) 」には、必要に応じて変更できるサンプルテンプレートがいくつか含まれています。

</div>

<div>

## <a name="best-practices"></a>ベスト プラクティス

  - すべてのサーバー オペレーティング システムおよびアプリケーションを強化します。

  - サーバーのスナップショットを保護し、すべての仮想サーバーのセキュリティを強化します。

  - グループ ポリシーを使用して、セキュリティ ロックダウンを実装します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

