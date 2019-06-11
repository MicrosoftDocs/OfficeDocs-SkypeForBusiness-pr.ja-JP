---
title: 'Lync Server 2013: 統合連絡先ストアを使用するように Lync Server を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79c26321945444bcf5d450a7397fefb244223ec0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a>ユニファイド連絡先ストアを使用するように Microsoft Lync Server 2013 を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-07_

ユニファイド連絡先の保存機能を使用すると、ユーザーは1つの連絡先リストを管理できるようになり、Microsoft Lync 2013、Microsoft Outlook 2013、Microsoft Outlook Web App 2013 などの複数のアプリケーションでそれらの連絡先を使用できるようになります。 ユーザーに対してユニファイド連絡先ストアを有効にした場合、そのユーザーの連絡先は Microsoft Lync Server 2013 に保存されず、SIP プロトコルを使用して取得されます。 代わりに、彼の連絡先は Microsoft Exchange Server 2013 に保存され、Exchange Web Services を使用して取得されます。

<div>


> [!NOTE]  
> 技術的には、連絡先情報は、ユーザーの Exchange 2013 メールボックスにある一対のフォルダーに格納されています。 連絡先自体は、エンドユーザーに表示される Lync の連絡先という名前のフォルダーに保存されます。連絡先に関するメタデータは、エンドユーザーに表示されないサブフォルダーに格納されます。



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a>ユーザーに対して統合連絡先ストアを有効にする

Lync Server 2013 と Exchange 2013 の間でサーバー間認証を既に構成している場合は、統合連絡先ストアの使用も有効になっています。追加のサーバー構成は必要ありません。 ただし、ユーザーの連絡先を統合連絡先ストアに移動するために、追加のユーザー アカウント構成を行う必要があります。 既定では、ユーザーの連絡先は Lync Server に保存され、ユニファイド連絡先ストアには保持されません。

統合連絡先ストアへのアクセスは、Lync Server ユーザーサービスポリシーを使って管理されます。 ユーザーサーバーポリシーには、1つのプロパティしかありません (UcsAllowed)。このプロパティは、ユーザーの連絡先が保存されている場所を決定するために使用されます。 ユーザーが、UcsAllowed が True ($True) に設定されているユーザーサービスポリシーによって管理されている場合、ユーザーの連絡先はユニファイド連絡先ストアに保存されます。 ユーザーが、UcsAllowed が False ($False) に設定されているユーザーサービスポリシーによって管理されている場合、そのユーザーの連絡先は Lync Server に保存されます。

Lync Server 2013 をインストールすると、(グローバルスコープで構成された) 1 つのユーザーサービスポリシーもインストールされます。 このポリシーの UcsAllowed 値は True に設定されていて、ユーザーの連絡先は既定で統合連絡先ストアに格納されます (統合連絡先ストアを展開および構成済みであることが前提です)。 ユーザーの連絡先をすべて統合連絡先ストアに移行したい場合、他の操作を行う必要はありません。

すべての連絡先を統合連絡先ストアに移行しない場合は、すべてのユーザーに対して統合連絡先ストアを無効にできます。その場合は、グローバル ポリシーの UcsAllowed プロパティを False に設定します。

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

グローバルポリシーでユニファイド連絡先ストアを無効にした後は、統合された連絡先ストアの使用を有効にするユーザーごとのポリシーを作成できます。これにより、他のユーザーが引き続き Lync Server に連絡先を保持しているときに、一部のユーザーをユニファイド連絡先ストアに残しておくことができます。 次のようなコマンドを使用して、ユーザーごとのユーザーサービスポリシーを作成できます。

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

新しいポリシーを作成した後、そのポリシーを、統合連絡先ストアへのアクセス権を必要とするすべてのユーザーに割り当てる必要があります。ユーザーごとのポリシーをユーザーに割り当てるには、次のようなコマンドを使用します。

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

ポリシーが割り当てられると、Lync Server によって、ユーザーの連絡先がユニファイド連絡先ストアに移行されます。 移行が完了すると、ユーザーは Lync Server ではなく、Exchange に保存された連絡先になります。 移行が完了した時点でユーザーが Lync 2013 にログオンしている場合は、メッセージボックスが表示され、その後、プロセスを完了するために Lync からログオフしてからもう一度ログインするように求められます。 ユーザーごとのポリシーを割り当てられないユーザーの連絡先は、統合連絡先ストアに移行されません。 そのようなユーザーはグローバル ポリシーで管理され、グローバル ポリシーでは統合連絡先ストアの使用が無効になっているためです。

Lync Server 管理シェル内から[CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)コマンドレットを実行することで、ユーザーの連絡先が正常に統合された連絡先ストアに移行されたことを確認できます。

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

Test-CsUnifiedContactStore が成功すれば、統合連絡先ストアへのユーザー sip:kenmyer@litwareinc.com の連絡先の移行は完了しています。

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a>統合連絡先ストアのロールバック

ユーザーの連絡先を、統合された連絡先ストアから削除する必要がある場合 (たとえば、Microsoft Lync Server 2010 上でユーザーがホームポイントを使用する必要があり、そのため、ユニファイド連絡先ストアを使用できなくなった場合) は、2つの操作を行う必要があります。 最初に、ユーザーに、ユニファイド連絡先ストアで連絡先を保存することを禁止する新しいユーザーサービスポリシーを割り当てる必要があります。 (これは、UcsAllowed プロパティが $False に設定されているポリシーです。)このようなポリシーがない場合は、次のようなコマンドを使用して作成できます。

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

その後、次のようなコマンドを使用して、この新しいユーザーごとのポリシー (NoUnifiedContactStore) を割り当てます。

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

上記のコマンドは、ユーザー Ken Myer に新しいポリシーを割り当てると共に、Ken の連絡先が統合連絡先ストアに移行されないようにします。

<div>


> [!NOTE]  
> 場合によっては、ユーザーの現在のユーザーサービスポリシーを割り当て解除するだけで、同じような結果を得ることができます。 たとえば、統合連絡先ストアを有効にするユーザーごとのユーザー サービス ポリシーが Ken Myer に割り当てられているが、グローバル ポリシーでは統合連絡先ストアの使用が禁止されているとします。 その場合は、Ken のユーザーごとのサービスポリシーを割り当て解除することができます。 それにより、Ken は自動的にグローバル ポリシーによって管理されるようになるため、統合連絡先ストアにはアクセスできなくなります。<BR>以前に割り当てられたユーザーのポリシーを割り当て解除するには、前に示したのと同じコマンドを使用しますが、今回は PolicyName パラメーターを null 値に設定します。<BR>Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null



</div>

統合連絡先ストアを使用する場合は、"Ken の連絡先が統合連絡先ストアに移行されないようにする" という点に注意することが重要です。 単純に新しいユーザー サービス ポリシーを Ken に割り当てるだけでは、Ken の連絡先は統合連絡先ストアから移動されません。 ユーザーが Lync Server 2013 にログオンすると、システムはユーザーのユーザーサービスポリシーをチェックして、ユーザーの連絡先をユニファイド連絡先ストアに保持する必要があるかどうかを確認します。 答えが「はい」である (つまり、UcsAllowed プロパティが $True に設定されている) 場合は、連絡先が統合連絡先ストアに移行されます (連絡先がまだ統合連絡先ストアに移動されていないと仮定します)。 回答が「いいえ」の場合、Lync Server はユーザーの連絡先を無視し、次のタスクに進みます。 つまり、Lync Server は、UcsAllowed プロパティの値に関係なく、ユーザーの連絡先を統合された連絡先ストアから自動的に移動しないことを意味します。

つまり、ユーザーに新しいユーザーサービスポリシーを割り当てると、 [CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)コマンドレットを実行して、ユーザーの連絡先を Exchange 2013 から移動して、Lync Server 2013 に戻す必要があります。 たとえば、Ken Myer に新しいユーザー サービス ポリシーを割り当てた後、次のコマンドを使用して Ken の連絡先を統合連絡先ストアから移動できます。

    Invoke-CsUcsRollback -Identity "Ken Myer"

ユーザーサービスのポリシーを変更しても、CsUcsRollback コマンドレットを実行しない場合、Ken の連絡先はユニファイド連絡先ストアから削除されません。 CsUcsRollback を実行しても、Ken Myer のユーザーサービスポリシーを変更しない場合はどうすればよいですか? その場合、Ken の連絡先はユニファイド連絡先ストアから一時的に削除されます。 この削除は一時的なものであるということを念頭に置いておくことが重要です。 Ken の連絡先がユニファイド連絡先ストアから削除されると、Lync Server 2013 は7日待ってから、Ken に割り当てられているユーザーサービスポリシーを確認します。 この統合された連絡先ストアのユーザーを有効にするポリシーが Ken に割り当てられている場合、その連絡先は自動的に連絡先ストアに戻されます。 ユニファイド連絡先ストアから連絡先を完全に削除するには、CsUcsRollback コマンドレットを実行するだけでなく、ユーザーサービスのポリシーを変更する必要があります。

移行には多くの変数が影響するため、統合連絡先ストアにアカウントが完全に移行されるまでの時間を予想することは困難です。しかし、一般的には、移行が即座に有効になることはありません。移行する連絡先の数が少ない場合でも、完了するまでに 10 分以上かかることもあります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

