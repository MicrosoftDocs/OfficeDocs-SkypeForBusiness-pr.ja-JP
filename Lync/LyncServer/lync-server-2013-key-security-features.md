---
title: 'Lync Server 2013: 主なセキュリティ機能'
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
ms.openlocfilehash: 20205bb401132143b0bcda28343e4ae3bcfd93b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a>Lync Server 2013 の主なセキュリティ機能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-18_

Lync Server 2013 には、サーバー間認証、役割ベースのアクセス制御、構成データの集中化されたストレージなど、いくつかのセキュリティ機能があります。

この記事では、Lync Server 2013 のセキュリティの概要について説明します。

<div>

## <a name="key-security-features-in-lync-server-2013"></a>Lync Server 2013 の主なセキュリティ機能

セキュリティは非常に広範なトピックです。 Lync Server 2013 のすべての機能に加えて、Lync エコシステムを構成するデータベース、サービス、ハードウェアのセキュリティが確保されます。 この記事では、セキュリティを目的として設計された Lync Server 2013 の一部の機能について説明します。

<div>

## <a name="planning-and-design-tools"></a>計画およびデザインツール

Lync Server 2013 には、計画と設計を促進し、Lync Server コンポーネントを誤って構成する機会を減らすための2つのツールが用意されています。

  - トポロジ**計画ツール**は、多くのトポロジ設計プロセスを自動化します。 計画ツールの結果をトポロジビルダーにエクスポートできます。これは、Lync Server 2013 を実行している各サーバーをインストールするために必要なツールです。

  - **トポロジビルダー**は、すべての構成情報を中央管理ストアに格納します。

これらのツールの詳細については、「 [Planning For Lync Server 2013](lync-server-2013-planning.md)」を参照してください。

</div>

<div>

## <a name="central-management-store"></a>中央管理ストア

Lync Server 2013 では、サーバーとサービスに関する構成データは中央管理ストアに含まれています。 中央管理ストアは、Lync Server 展開の定義、セットアップ、管理、管理、説明、および運用に必要なデータの堅牢で schematized ストレージを提供します。 また、CMS はこのデータを検証して構成の一貫性も保証します。 この構成データに加えられたすべての変更は中央管理ストアで行われるため、"同期ができません" の問題が発生しなくなります。

このデータの読み取り専用のコピーは、エッジ サーバーを含めたトポロジ内のすべてのサーバーにレプリケートされます。 レプリケーションは、既定でネットワークサービスのコンテキスト下で実行されるサービスによって管理されます。これにより、コンピューター上の単純なユーザーの権限とアクセス許可が減少します。

</div>

<div>

## <a name="server-to-server-authentication"></a>サーバー間認証

Lync Server 2013 では、Open Authorization (OAuth) プロトコルを使用して、サーバー間で認証を構成できます。 たとえば、Exchange Server 2013 を実行しているサーバーでの認証を行うように Lync Server 2013 を構成できます。 Lync server と Exchange サーバーは、OAuth プロトコルを使用して相互に信頼することができます。 これにより、シームレスな方法で製品を統合することができます。 詳細については、「 [Lync server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell ベースの管理および Web ベースの管理インターフェイス

Lync Server 2013 は、Windows PowerShell コマンドラインインターフェイス上に構築された強力な管理インターフェイスを提供します。 これにはセキュリティを管理するためのコマンドレットが含まれており、ユーザーが簡単にまたは知らないうちにスクリプトを実行できないように、Windows PowerShell のセキュリティ機能が既定で有効になっています。 つまり、セキュリティを最大限に高め、攻撃の手段を減少させるように、ソフトウェアの既定値が自動的に設定されています。 Lync Server 2013 での Windows PowerShell 管理サポートの詳細については、「 [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md)」を参照してください。

</div>

<div>

## <a name="role-based-access-control-rbac"></a>役割ベースのアクセス制御 (RBAC)

Microsoft Lync Server 2013 は、役割ベースのアクセス制御 (RBAC) を提供して、セキュリティの高い標準を維持しながら管理タスクを委任できるようにします。 業務上必要な管理権限のみをユーザーに与える "最小限の特権" の原則に従って RBAC を使用することができます。 Lync Server 2013 には、新しい役割を作成したり、既存の役割を変更したりする機能が導入されています。 詳細については、「 [Lync Server 2013 での役割ベースのアクセス制御の計画](lync-server-2013-planning-for-role-based-access-control.md)」を参照してください。

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a>ネットワークアドレス変換 (NAT)

Lync Server 2013 は、エッジサーバーの内部インターフェイスでのネットワークアドレス変換 (NAT) の使用をサポートしていませんが、アクセスエッジサービス、Web 会議エッジサービス、および音声ビデオエッジサービスの外部インターフェイスを、単一および拡張統合エッジサーバートポロジの両方でネットワークアドレス変換 (NAT) を実行するルーターまたはファイアウォールの背後に配置することをサポート ロードバランサー機器の背後にある複数のエッジサーバーは、NAT を使用できません。 複数のエッジサーバーが外部インターフェイスで NAT を使用している場合は、ドメインネームシステム (DNS) 負荷分散が必要です。 さらに、DNS 負荷分散を使用すると、エッジサーバープール内のエッジサーバーごとのパブリック IP アドレスの数を減らすことができます。 詳細については、「[Lync Server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)」を参照してください。

<div>


> [!NOTE]  
> Microsoft Office Communications Server 2007 の展開があり、企業とフェデレーションエンタープライズとの間で音声ビデオを使用する必要がある企業とフェデレーションを行う場合、ポート要件は展開された旧バージョンのエッジサーバー用のものになります。 たとえば、フェデレーションパートナーがエッジサーバーを Lync Server 2013 にアップグレードするまで、これらの古いバージョンに必要なポート範囲を両方のエンタープライズに対して開く必要があります。 その時点で、ポート要件を確認し、新しい構成に応じて減少できます。



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a>エッジサーバーの簡略化された証明書

展開ウィザードはサブジェクト名 (SN) およびサブジェクト代替名 (SAN) を自動的に読む込むことができるため、不要で、安全でない可能性があるエントリを含める危険性が減少します。

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>信頼できるコンピューティングのセキュリティ開発ライフサイクル (SDL)

Lync Server 2013 は、「」に<https://go.microsoft.com/fwlink/?linkid=68761>記載されている「Microsoft の信頼できるコンピューティングのセキュリティ開発ライフサイクル (SDL)」に準拠して設計および開発されています。

  - **信頼できる設計**   による信頼性の高い統合コミュニケーションシステムを作成するための最初の手順は、脅威モデルを設計し、設計された各機能をテストすることでした。 さらに、Microsoft は、予期しない製品の動作から生じるセキュリティの脆弱性を検出するために、設計された動作の外部でのテストを行います。 複数のセキュリティ関連の改善点がコーディング プロセスとコーディング手法に組み込まれました。 コードが最終的な製品にチェックインされる前に、ビルド時ツールにより、バッファー オーバーランおよびその他のセキュリティ脅威の可能性を検出します。 もちろん、すべての未知のセキュリティ脅威を防ぐように設計することは不可能です。 完全なセキュリティを保証できるシステムはありません。 ただし、製品の開発は開始時にセキュリティ保護された設計原則を採用しているため、Lync Server 2013 には、そのアーキテクチャの基本的な部分として業界標準のセキュリティテクノロジが組み込まれています。

  - **既定**   では、Lync Server 2013 でのネットワーク通信は暗号化されています。 すべてのサーバーで証明書と Kerberos 認証、TLS、セキュアリアルタイム転送プロトコル (SRTP)、およびその他の業界標準の暗号化手法 (128 ビット Advanced Encryption Standard (AES) 暗号化を含む) が使用されているため、ほぼすべての Lyncサーバーデータはネットワーク上で保護されます。 また、役割ベースのアクセス制御を使用すると、Lync Server 2013 を実行しているサーバーを展開して、各サーバーの役割がサービスのみを実行し、そのサービスに関連するアクセス許可のみをサーバーの役割に適したように展開することができます。

  - **展開による信頼**   度の高いすべての Lync Server 2013 のドキュメントには、展開に最適なセキュリティレベルを決定および構成し、既定以外のオプションをアクティブ化する際のセキュリティリスクを評価するのに役立つベストプラクティスと推奨事項が含まれています。

</div>

</div>

<span> </span>

</div>

</div>

</div>

