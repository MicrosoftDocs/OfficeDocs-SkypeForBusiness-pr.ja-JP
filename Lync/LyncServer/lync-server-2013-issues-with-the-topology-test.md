---
title: 'Lync Server 2013: トポロジテストの問題'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d416aac6460870ab14d5296bcc6c7944ecf699e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a>Lync Server 2013 でのトポロジテストの問題

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

ベストプラクティスアナライザーは、**テスト-CsTopology**コマンドレットと同様に、Lync Server 2013 がグローバルレベルで正常に機能しているかどうかを確認するための手段を提供します。 既定では、コマンドレットなどのベストプラクティスアナライザーは、Lync Server 2013 インフラストラクチャ全体をチェックし、必要なサービスが実行されていること、およびこれらのサービスとユニバーサル用に適切なユーザー権限と権限が設定されていることを確認します。Lync Server 2013 をインストールしたときに作成されるセキュリティグループ。

Lync Server 全体としての有効性を確認するだけでなく、**テスト用**に、特定のサービスの有効性も確認します。 コマンドレットを使用して特定のサービスをテストする方法について詳しくは、「Lync Server 管理シェルドキュメント」の「[テスト-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology)使い方」をご覧ください。 以下の情報を参考にして、トポロジの問題を解決してください。

<div>


> [!NOTE]  
> ベストプラクティスアナライザーは、エッジサーバーの構成と、ファイアウォールの設定やアクセス許可を含む、関連する境界ネットワーク設定に応じて、エッジサーバーにアクセスしてスキャンできない場合があります。 スキャンにエッジサーバーが含まれていて、エッジサーバーへのアクセスに問題があるという報告があった場合は、[<STRONG>エッジサーバー</STRONG> ] チェックボックスをオフにし、もう一度スキャンを実行して、問題がレポートに表示されないようにします。



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a>トポロジの問題を解決する

トポロジテストでトポロジの問題が検出された場合、この問題は、トポロジを公開または有効にしたときに発生した問題が原因である可能性があります。

トポロジに変更を加えた場合、変更は、公開されていて有効になっている場合にのみ有効になります。 トポロジを変更するには、トポロジビルダーを使用する必要があります。 変更を加えた後は、トポロジビルダーを使用して、変更を発行して有効にすることができます。

変更を公開すると、新しい情報 (たとえば、新しいサイトまたは新しいサーバーの役割) が中央管理ストアに書き込まれます。 ただし、これらの新規 (または新しく更新された) オブジェクトは、すぐにトポロジに参加することはできません。 更新されたトポロジを有効にした場合にのみ、オブジェクトはトポロジに参加します。 トポロジビルダーで [発行] オプションを選択した場合、次の手順のいずれかが行われます。変更は公開されます (つまり、中央管理ストアに作成されます)。次に、新しいトポロジが有効になります。

既定では、RTCUniversalServerAdmins グループのメンバーは、 **Publish/cstopology**コマンドレットと**Enable-cstopology**コマンドレットを実行することを許可されています。 ただし、セットアップのアクセス許可が委任されていない場合は、ドメイン管理者としてログオンして**発行-CsTopology**方法で実行する必要があります。 RTCUniversalServerAdmins を実際に使用する権利を与え**** られるようにするには、Lync Server サービスを実行しているコンピューターが含まれているすべての Active Directory コンテナーに対して、**グラント setuppermission**コマンドレットを実行する必要があります。 RTCUniversalServerAdmins を有効にするには、 **Enable-CsTopology**コマンドレットを使用する権利を付与するために、Lync Server サービスを実行しているコンピューターが含まれているすべての Active Directory ドメインサービスコンテナーに対して、 **Set-cssetuppermission**コマンドレットを実行する必要があります。 これは、トポロジビルダーを使用してトポロジを有効化および公開するために適用されることに注意してください。 **Set-CsSetupPermission**を使用してアクセス許可を委任していない場合は、トポロジビルダーを介してトポロジを有効にして発行できるのは、ドメイン管理者のみです。

</div>

</div>

<span> </span>

</div>

</div>

</div>

