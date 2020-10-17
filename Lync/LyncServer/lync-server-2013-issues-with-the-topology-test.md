---
title: 'Lync Server 2013: トポロジテストに関する問題'
description: 'Lync Server 2013: トポロジテストに関する問題。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a0f24942844bcf371eff94ee04c8faafcf513d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554443"
---
# <a name="issues-with-the-topology-test-in-lync-server-2013"></a>Lync Server 2013 のトポロジテストに関する問題

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

**Test-CsTopology**コマンドレットと同様に、ベストプラクティスアナライザーは Lync Server 2013 がグローバルレベルで正常に機能していることを確認する方法を提供します。 既定では、コマンドレットなどのベストプラクティスアナライザーは、Lync Server 2013 インフラストラクチャ全体をチェックし、必要なサービスが実行されていること、およびこれらのサービスに対して適切なユーザー権限とアクセス許可が設定されていること、および Lync Server 2013 のインストール時に作成されたユニバーサルセキュリティグループに対して適切なユーザー権限とアクセス許可

Lync Server 全体としての有効性を検証するだけでなく、特定のサービスの **有効性も確認** します。 コマンドレットを使用して特定のサービスをテストする方法の詳細については、「Lync Server Management Shell」のドキュメントの「 [テスト-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) 方法」を参照してください。 トポロジの問題の解決については、以下の情報を参考にしてください。

<div>


> [!NOTE]  
> エッジ サーバーの構成および関連する境界ネットワークの設定 (ファイアウォールの設定とアクセス許可など) によっては、ベスト プラクティス アナライザーがエッジ サーバーにアクセスしてスキャンできない場合があります。エッジ サーバーがスキャンに含まれていて、エッジ サーバーへのアクセスに問題があることが報告される場合は、[<STRONG>エッジ サーバー</STRONG>] チェック ボックスをオフにしてスキャンを再び実行し、問題がレポートに表示されないようにしてください。



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a>トポロジの問題の解決

トポロジ テストでトポロジに問題が見つかった場合、トポロジを公開または有効化するときに発生した問題が原因である可能性があります。

トポロジを変更すると、公開して有効にするまで、その変更は反映されません。 トポロジの変更を行うには、トポロジビルダーを使用する必要があります。 変更した後は、トポロジビルダーを使用して、これらの変更を公開して有効にすることができます。

変更を公開すると、新しい情報 (たとえば、新しいサイトまたは新しいサーバーの役割) が中央管理ストアに書き込まれます。 ただし、これらの新しい (または新しく変更された) オブジェクトは、すぐにはトポロジに参加しません。 オブジェクトは、更新されたトポロジを有効にした場合にのみ、トポロジに参加します。 トポロジビルダーで [発行] オプションを選択した場合、次の両方の手順が実行されます。変更が発行されます (つまり、中央管理ストアに書き込まれます)。その後、新しいトポロジが有効になります。

既定では、RTCUniversalServerAdmins グループのメンバーは、**Publish-CsTopology** コマンドレットおよび **Enable-CsTopology** コマンドレットの実行を許可されてます。 ただし、セットアップ アクセス許可が委任されていない場合は、ドメイン管理者としてログオンし、**Publish-CsTopology** を実行する必要があります。 RTCUniversalServerAdmins コマンドレットを実際に使用する権限を付与する **には、** Lync Server サービスを実行しているコンピューターが含まれるすべての Active Directory コンテナーで、 **Grant-cssetuppermission** コマンドレットを実行する必要があります。 RTCUniversalServerAdmins **コマンドレットを** 使用する権限を付与するには、Lync Server サービスを実行しているコンピューターが含まれるすべての Active Directory ドメインサービスコンテナーに対し **て、コマンドレットを** 実行する必要があります。 このことは、トポロジビルダーを使用したトポロジの有効化と公開に適用されることに注意してください。 **Set-CsSetupPermission**を使用してアクセス許可を委任していない場合は、トポロジビルダーを使用してトポロジを有効にして公開できるのはドメイン管理者のみになります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

