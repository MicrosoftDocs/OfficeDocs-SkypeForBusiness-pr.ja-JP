---
title: 'Lync Server 2013: バックアップの実行と監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b79fdbaceff06155389d101570b23d6143b9bbcc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536754"
---
# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>Lync Server 2013 でのバックアップの実行と監視

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-15_

業務上の優先度によって、組織のバックアップと復元の要件を規定する必要があります。 サーバーとデータのバックアップを実行することは、障害を計画するための最初の防御線です。

Lync Server 2013 サービスまたはサーバーの役割を実行しているコンピューターは、現在のトポロジ、現在の構成設定、および現在のポリシーのコピーを持っている必要があります。その前に、指定された役割で機能することができます。 Lync Server は、この情報が必要な各コンピューターに渡されていることを確認する責任があります。

中央管理ストアのアップグレード時に、Lync Server トポロジ、構成設定、およびポリシーをバックアップおよび復元するには、 **Export-csconfiguration** および **Import-csconfiguration** コマンドレットを使用します。 **Export-CsConfiguration**コマンドレットを使用すると、データをにエクスポートできます。ZIP ファイル。 その後、 **インポート-CsConfiguration** コマンドレットを使用して、このを読み取ることができます。ZIP ファイルを復元し、トポロジ、構成設定、およびポリシーを中央管理ストアに復元します。 その後、Lync server のレプリケーションサービスは、復元された情報を Lync Server サービスを実行している他のコンピューターにレプリケートします。

構成データをエクスポートおよびインポートする機能は、境界ネットワーク (たとえば、エッジサーバー) に配置されているコンピューターの初期構成時にも使用されます。 境界ネットワーク内のコンピューターを構成する場合は、最初に CsConfiguration コマンドレットを使用して手動でレプリケーションを実行する必要があります。 **エクスポート-CsConfiguration** を使用して構成データをエクスポートし、をコピーする必要があります。境界ネットワーク内のコンピューターへの ZIP ファイル。 その後、 **import-CsConfiguration** および localstore パラメーターを使用してデータをインポートできます。 この操作は一度だけ実行する必要があります。 その後は、レプリケーションが自動的に実行されます。

このコマンドレットを実行できるユーザー: 既定 **では、RTCUniversalServerAdmins コマンドレットを** ローカルで実行する権限があるのは、次のグループのメンバーです。 すべての RBAC の役割の一覧を返すには、このコマンドレットを (自分で作成したカスタムの RBAC の役割を含む) に割り当てられているので、Windows PowerShell プロンプトから次のコマンドを実行します。

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

すべての SQL 2012 バックエンドデータベースは、 [sql のベストプラクティス](https://go.microsoft.com/fwlink/p/?linkid=290716)に従ってバックアップする必要があります。

Lync Server 2013 インフラストラクチャの障害復旧計画を定期的にテストするには、運用環境をできるだけ忠実に再現するラボ環境で実行する必要があります。 障害復旧テストの詳細については、「月次タスク」を参照してください。

バックアップの頻度は、復元ポイントと回復ポイントの目標に基づいて調整できます。 ベストプラクティスとして、毎日定期的に定期的なスナップショットを取得します。 通常、完全バックアップは24時間ごとに実行する必要があります。

<div>

## <a name="see-also"></a>関連項目


[インポート-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[エクスポート-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[SQL のベストプラクティス](https://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

