---
title: 'Lync Server 2013: バックアップの実行と監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fffc6a8355305e11d87513ffc37626f3e386c749
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>Lync Server 2013 でのバックアップの実行と監視

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-15_

ビジネス優先度によって、組織のバックアップと復元の要件を指定する必要があります。 サーバーとデータのバックアップを実行することが、障害の計画での第1の防御線です。

Lync Server 2013 サービスまたはサーバーロールを実行しているコンピューターには、現在のトポロジ、現在の構成設定、および現在のポリシーのコピーが、指定された役割で機能するために必要です。 Lync Server は、この情報が必要な各コンピューターに渡されることを確認する責任を負います。

**エクスポート-csconfiguration**コマンドレットと**インポート-csconfiguration**コマンドレットを使用して、一元管理ストアアップグレード中の Lync Server のトポロジ、構成設定、ポリシーをバックアップおよび復元します。 **エクスポート-CsConfiguration**コマンドレットを使用して、データをにエクスポートできます。ZIP ファイル。 次に、**インポート-CsConfiguration**コマンドレットを使用して、これを読み取ります。ZIP ファイルを保存して、トポロジ、構成設定、ポリシーを中央管理ストアに復元します。 その後、Lync server のレプリケーションサービスは、復元された情報を Lync Server サービスを実行している他のコンピューターに複製します。

構成データをエクスポートおよびインポートする機能は、境界ネットワーク (たとえば、エッジサーバー) に配置されているコンピューターの最初の構成時にも使用されます。 境界ネットワークでコンピューターを構成する場合は、まず、CsConfiguration コマンドレットを使用して手動でレプリケーションを実行する必要があります。**エクスポート-CsConfiguration**を使用して構成データをエクスポートし、をコピーする必要があります。境界ネットワークのコンピューターに ZIP ファイルを保存します。 その後、 **import-CsConfiguration**と localstore パラメーターを使ってデータをインポートできます。 この操作は1回だけ実行する必要があります。 その後、複製が自動的に実行されます。

このコマンドレットを実行できるのはどのユーザーですか。既定では、次のグループのメンバーは、ローカルで**エクスポートと CsConfiguration**コマンドレットを実行することを許可されています。 RTCUniversalServerAdmins すべての RBAC ロールの一覧を返すには、このコマンドレットが (自分自身で作成したすべてのカスタム RBAC ロールを含む) に割り当てられ、Windows PowerShell プロンプトから次のコマンドを実行します。

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

すべての SQL 2012 バックエンドデータベースは、 [sql のベストプラクティス](http://go.microsoft.com/fwlink/p/?linkid=290716)に従ってバックアップする必要があります。

Lync Server 2013 インフラストラクチャの障害回復計画を定期的にテストすることは、実稼働環境にできるだけ近いラボ環境で行う必要があります。 障害回復テストの詳細については、「月次タスク」を参照してください。

復元ポイントと回復ポイントの目標に基づいて、バックアップの頻度を調整できます。 ベストプラクティスとして、日常的に定期的にスナップショットを取ることをお勧めします。 通常、フルバックアップは24時間ごとに実行する必要があります。

<div>

## <a name="see-also"></a>関連項目


[インポート-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[エクスポート-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[SQL のベストプラクティス](http://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

