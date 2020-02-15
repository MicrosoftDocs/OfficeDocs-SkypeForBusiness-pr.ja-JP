---
title: 'Lync Server 2013: バックエンドサーバーの高可用性'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7313d11557344586910f6afeeb5422744207023
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a>Lync Server 2013 のバックエンドサーバーの高可用性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-08-12_

バックエンドサーバーの高可用性を確保するために、同期 SQL ミラーリングまたは SQL クラスタリングのどちらかを使用できます。 これらのソリューションのいずれかをオプションで使用しますが、組織のビジネス継続性を維持することをお勧めします。 Lync Server 2013 のバックエンドサーバーの高可用性については、非同期 SQL ミラーリングはサポートされていません。 これ以降、特に指定がない限り、SQL ミラーリングは同期 SQL ミラーリングを意味するものとします。

トポロジビルダーを使用して、SQL ミラーリングを簡単にセットアップできます。 SQL フェールオーバークラスタリングでは、セットアップに SQL Server を使用する必要があります。

障害復旧用の別のフロントエンドプールとペアになっているプールで SQL ミラーリングまたは SQL クラスタリングのいずれかを使用する場合は、両方のプールで同じバックエンド高可用性ソリューションを使用する必要があります。 SQL クラスタリングを使用して、プールと SQL ミラーリングを使用してプールをペアにすることはできません。

SQL ミラーリングを展開すると、プール内のすべての Lync Server データベースがミラーリングされます。これには、中央管理ストア (このプールに配置されている場合)、応答グループアプリケーションデータベースおよびコールパークアプリケーションデータベース (それらのアプリケーションの場合) などがあります。がプールで実行されている。

SQL ミラーリングでは、サーバーに対して共有ストレージを使用する必要はありません。各サーバーは、データベースのコピーをローカル ストレージに保持しします。

SQL ミラーリングの展開では、監視を使用することも使用しないこともできます。バックエンド サーバーのフェールオーバーが自動的になるので、監視を使用することをお勧めします。使用しない場合は、管理者が手動でフェールオーバーを実行する必要があります。監視を展開した場合でも、管理者は必要に応じてバックエンド サーバーのフェールオーバーを手動で開始できます。

監視を使用する場合は、バックエンド サーバーの複数のペアに対して 1 つの監視を使用できます。監視とバックエンド サーバーのペアを 1 対 1 で対応させる必要はありません。ただし、バックエンド サーバーの複数のペアに対して 1 つの監視を使用する展開は、ペアごとに異なる監視を使用するトポロジほど復元性が高くありません。

SQL クラスタリングのサポートの詳細については、「 [Lync Server 2013 のデータベースソフトウェアサポート](lync-server-2013-database-software-support.md)」を参照してください。 SQL クラスタリングの展開の詳細については、「 [CONFIGURE Sql Server クラスタリング For Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)」を参照してください。

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a>SQL ミラーリングによるバックエンドサーバーの自動フェールオーバーの復旧時間

SQL ミラーリングを使用した自動バックエンドフェールオーバーの場合、目標復旧時間 (RTO) のエンジニアリング目標は5分です。 同期 SQL ミラーリングなので、バックエンド サーバー障害の間にデータ損失が発生する可能性は、サーバー間のデータ移動中にフロントエンド サーバーとバックエンド サーバーの両方が同時にダウンするという希な状況を除き、ありません。 目標復旧ポイント (RPO) のエンジニアリング目標は 5 分です。

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a>SQL ミラーリングでバックエンドサーバー障害が発生したときのユーザー環境

障害の間のユーザー エクスペリエンスは、障害の特徴とトポロジによって異なります。

SQL ミラーリングを使用し、監視を構成していて、プリンシパルに障害が発生した場合、バックエンドサーバーのフェールオーバーは自動的に、かつ迅速に行われます。 使用中のユーザーがセッションで大きな中断を感じることはありません。

監視が構成されていない場合は、管理者が手動でフェールオーバーを起動するまでにしばらく時間がかかります。 その間、アクティブユーザーが影響を受ける可能性があります。 約30分間は通常どおりセッションを続行します。 プライマリが依然として復元されていない場合、または管理者がバックアップにフェールオーバーしていない場合、ユーザーは復元モードに切り替わります。つまり、Lync Server で永続的な変更を必要とするタスク (連絡先の追加など) を実行できなくなります。

プリンシパルとミラーの両方のバックエンド サーバーで障害が発生した場合、またはどちらかのサーバーと監視で障害が発生した場合は、バックエンド サーバーは使用できなくなります (プリンシパルがまだ動作していたとしても)。この場合、使用中のユーザーはしばらくしてから復元モードに切り替えられます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

