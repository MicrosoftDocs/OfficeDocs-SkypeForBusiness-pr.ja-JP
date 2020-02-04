---
title: 'Lync Server 2013: セキュリティの主要機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55d59a6978b90db82ccf899df90b05c739e71a57
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a>Lync Server 2013 の主要なセキュリティ機能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-07-18_

Lync Server 2013 には、サーバー間認証、役割ベースのアクセス制御、構成データの一元ストレージなど、いくつかのセキュリティ機能が含まれています。

この記事では、Lync Server 2013 セキュリティの概要について説明します。

<div>

## <a name="key-security-features-in-lync-server-2013"></a>Lync Server 2013 の主要なセキュリティ機能

セキュリティは非常に広い範囲に及ぶトピックです。 Lync Server 2013 のすべての機能、および Lync エコシステムを構成するデータベース、サービス、ハードウェアにセキュリティが設定されます。 この記事では、特にセキュリティのために設計された Lync Server 2013 の一部の機能について説明します。

<div>

## <a name="planning-and-design-tools"></a>計画ツールと設計ツール

Lync Server 2013 には、計画と設計を容易にするためのツールが2つ用意されています。 Lync Server コンポーネントの構成が間違っている可能性があります。

  - **トポロジ計画ツール**は、トポロジ設計プロセスの大部分を自動化します。 計画ツールからトポロジビルダーに結果をエクスポートすることができます。これは、Lync Server 2013 を実行している各サーバーをインストールするために必要なツールです。

  - **トポロジ ビルダー**は、すべての構成情報を中央管理ストアに格納します。

これらのツールについて詳しくは、「 [Lync Server 2013 の計画](lync-server-2013-planning.md)」をご覧ください。

</div>

<div>

## <a name="central-management-store"></a>中央管理ストア

Lync Server 2013 では、サーバーとサービスに関する構成データは中央管理ストアに含まれています。 中央管理ストアでは、Lync Server の展開を定義、セットアップ、管理、管理、説明、操作するために必要なデータを schematized に保存します。 また、データを検証して構成の一貫性を保ちます。 構成データへの変更はすべて中央管理ストアでなされるので、"非同期" の問題を回避できます。

データの読み取り専用コピーは、エッジ サーバーや存続可能ブランチ アプライアンスなど、トポロジ内のすべてのサーバーにレプリケートされます。レプリケーションは、既定では、ネットワーク サービスのコンテキストで実行されるサービスが管理し、権限とアクセス許可が抑えられてコンピューター上の一般ユーザーと同じになります。

</div>

<div>

## <a name="server-to-server-authentication"></a>サーバー間認証

Lync Server 2013 では、Open Authorization (OAuth) プロトコルを使用してサーバー間で認証を構成することができます。 たとえば、Exchange Server 2013 を実行しているサーバーに対して認証するように Lync Server 2013 を構成することができます。 OAuth プロトコルを使用すると、Lync server と Exchange server が相互に信頼することができます。 これにより、製品をシームレスな方法で統合することができます。 詳細については、「 [Lync server 2013 でサーバー間認証 (OAuth) とパートナーアプリケーションを管理する](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell ベースの管理と Web ベースの管理インターフェイス

Lync Server 2013 は、Windows PowerShell コマンドラインインターフェイスに基づいて構築された強力な管理インターフェイスを提供します。 このインターフェイスにはセキュリティを管理するためのコマンドレットが含まれているうえ、Windows PowerShell のセキュリティ機能が既定で有効になっており、ユーザーが簡単にまたは知らないうちにスクリプトを実行することができないようになっています。 つまり、セキュリティを最大限に高め、攻撃の手段を減らすように、ソフトウェアの既定値が自動的に設定されています。 Lync Server 2013 での Windows PowerShell 管理のサポートについて詳しくは、「 [Lync server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)」をご覧ください。

</div>

<div>

## <a name="role-based-access-control-rbac"></a>役割ベースのアクセス制御 (RBAC)

Microsoft Lync Server 2013 では、役割ベースのアクセス制御 (RBAC) を利用して、セキュリティの高い標準を維持しながら管理タスクを委任できます。 そのため、業務上必要な管理権限のみをユーザーに与える "最小限の特権" の原則に従って RBAC を使用することができます。 Lync Server 2013 には、新しい役割を作成したり、既存の役割を変更したりする機能が導入されています。 詳細については、「 [Lync Server 2013 での役割ベースのアクセス制御の計画](lync-server-2013-planning-for-role-based-access-control.md)」を参照してください。

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a>ネットワーク アドレス変換 (NAT)

Lync Server 2013 は、エッジサーバーの内部インターフェイスでのネットワークアドレス変換 (NAT) の使用をサポートしていませんが、統合されたエッジサーバートポロジの1つとスケーリングの両方について、ネットワークアドレス変換 (NAT) を実行するルーターまたはファイアウォールでの外部インターフェイスの配置をサポートしています。 ハードウェア ロード バランサーの背後にある複数のエッジ サーバーでは、NAT を使用できません。 複数のエッジ サーバーの外部インターフェイスで NAT を使用する場合は、ドメイン ネーム システム (DNS) の負荷分散が必要です。 DNS 負荷分散を使用すると、エッジ サーバー プール内のエッジ サーバーあたりのパブリック IP アドレスの数を削減できます。 詳細については、「[Lync Server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)」を参照してください。

<div>


> [!NOTE]  
> Microsoft Office Communications Server 2007 が展開されているエンタープライズとフェデレーションを行うときに、使用しているエンタープライズとフェデレーション先のエンタープライズとの間で音声ビデオを使用する必要がある場合、ポート要件は、展開されているエッジ サーバーのうち、古い方のバージョン用の要件になります。 たとえば、これらの古いバージョンに必要なポート範囲は、フェデレーションパートナーがそのエッジサーバーを Lync Server 2013 にアップグレードするまで両方のエンタープライズで開く必要があります。 アップグレード後には、ポート要件を見直して、新しい構成に応じて削減できます。



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a>エッジ サーバーの簡単化された証明書

展開ウィザードは、サブジェクト名 (SN) やサブジェクト代替名 (SAN) を自動的に読む込むことができるので、安全ではない可能性のある不要なエントリを含める危険性が減少します。

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>信頼できるコンピューティングのセキュリティ開発ライフサイクル (SDL)

Lync Server 2013 は、「」で<http://go.microsoft.com/fwlink/?linkid=68761>説明されている Microsoft の信頼できるコンピューティングセキュリティ開発ライフサイクル (SDL) に準拠して設計および開発されています。

  - **信頼性**   の高い設計された統合コミュニケーションシステムを構築するための最初の手順は、脅威モデルを設計し、設計された各機能をテストすることでした。 Microsoft では加えて、設計動作以外でのテストも実施して、予期しない製品動作から生じるセキュリティ脆弱性を探しています。 コーディング プロセスとコーディング手法には、セキュリティに関連する複数の改善点が組み込まれていました。 ビルド時に使われるツールは、製品にコードが最終的にチェックインされる前にバッファ オーバーランなどの潜在的なセキュリティ上の脅威を検出します。 それでも、未知のセキュリティ上の脅威のすべてを防ぐように設計することは不可能です。 完全なセキュリティを保証できるシステムはありません。 ただし、製品開発では、開発者がセキュリティで保護された設計原則を採用しているため、Lync Server 2013 には、アーキテクチャの基礎として業界標準のセキュリティ技術が組み込まれています。

  - **既定で信頼できる**   既定では、Lync Server 2013 のネットワーク通信が暗号化されています。 すべてのサーバーでは、証明書と Kerberos 認証、TLS、セキュリティで保護されたリアルタイムトランスポートプロトコル (SRTP)、およびその他の業界標準の暗号化技法 (128 ビット Advanced Encryption Standard (AES) 暗号化など) が使用されているため、ほぼすべての Lyncサーバーデータはネットワーク上で保護されています。 さらに、役割ベースのアクセス制御によって、Lync Server 2013 を実行しているサーバーを展開して、各サーバーの役割がサービスのみを実行し、そのサービスに関連するアクセス許可のみをサーバーの役割に対して適切であるようにすることができます。

  - **展開により信頼できる**   すべての Lync Server 2013 ドキュメントには、展開に最適なセキュリティレベルを決定して構成し、既定以外のオプションをアクティブ化する場合のセキュリティリスクを評価するためのベストプラクティスと推奨事項が記載されています。

</div>

</div>

<span> </span>

</div>

</div>

</div>

