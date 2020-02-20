---
title: 'Lync Server 2013: 統合連絡先ストアを使用するように Lync Server を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21e39b9584dfc274e9cf525db85d50df6188fac0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a>統合連絡先ストアを使用するように Microsoft Lync Server 2013 を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-07_

統合連絡先ストアを使用すると、ユーザーは1つの連絡先リストを管理し、Microsoft Lync 2013、Microsoft Outlook 2013、Microsoft Outlook Web App 2013 などの複数のアプリケーションで連絡先を使用できるようになります。 ユーザーに対して統合連絡先ストアを有効にすると、ユーザーの連絡先は Microsoft Lync Server 2013 に保存されず、SIP プロトコルを使用して取得されます。 代わりに、その連絡先は Microsoft Exchange Server 2013 に格納され、Exchange Web サービスを使用して取得されます。

<div>


> [!NOTE]  
> 技術的には、連絡先情報は、ユーザーの Exchange 2013 メールボックスにあるペアのフォルダーに格納されます。 連絡先自体は、エンドユーザーに表示される Lync の連絡先という名前のフォルダーに保存されます。連絡先に関するメタデータは、エンドユーザーには表示されないサブフォルダーに格納されます。



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a>ユーザーに対して統合連絡先ストアを有効にする

Lync Server 2013 と Exchange 2013 の間のサーバー間認証が既に構成されている場合は、統合連絡先ストアの使用も有効になっています。追加のサーバー構成は必要ありません。 ただし、ユーザーの連絡先を統合連絡先ストアに移動するために、追加のユーザー アカウント構成を行う必要があります。 既定では、ユーザーの連絡先は、統合連絡先ストアではなく、Lync Server に保持されます。

統合連絡先ストアへのアクセスは、Lync Server ユーザーサービスポリシーを使用して管理されます。 ユーザーサーバーポリシーには、1つのプロパティのみがあります (UcsAllowed)。このプロパティは、ユーザーの連絡先が格納されている場所を決定するために使用されます。 UcsAllowed が True ($True) に設定されているユーザーサービスポリシーによってユーザーが管理されている場合は、ユーザーの連絡先が統合連絡先ストアに格納されます。 ユーザーが、UcsAllowed が False ($False) に設定されているユーザーサービスポリシーで管理されている場合、その連絡先は Lync Server に保存されます。

Lync Server 2013 をインストールすると、(グローバルスコープで構成されている) 単一のユーザーサービスポリシーもインストールされます。 このポリシーの UcsAllowed 値は True に設定されています。つまり、既定では、ユーザーの連絡先が統合連絡先ストアに保存されます (これが展開および構成されていることが前提です)。 すべてのユーザーの連絡先を統合連絡先ストアに移行する場合は、何もする必要はありません。

すべての連絡先を統合連絡先ストアに移行しない場合は、グローバルポリシーの UcsAllowed プロパティを False に設定することによって、すべてのユーザーの統合連絡先ストアを無効にすることができます。

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

グローバルポリシーで統合連絡先ストアを無効にした後、統合連絡先ストアの使用を有効にするユーザーごとのポリシーを作成できます。これにより、他のユーザーが引き続き Lync Server に連絡先を保持しながら、一部のユーザーに自分の連絡先を統合連絡先ストアに保持させることができます。 次のようなコマンドを使用して、ユーザーごとのユーザーサービスポリシーを作成できます。

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

新しいポリシーを作成した後、そのポリシーを、統合連絡先ストアへのアクセス権を必要とするすべてのユーザーに割り当てる必要があります。ユーザーごとのポリシーをユーザーに割り当てるには、次のようなコマンドを使用します。

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

ポリシーに Lync Server が割り当てられると、ユーザーの連絡先が統合連絡先ストアに移行されます。 移行が完了した後、ユーザーは Lync Server ではなく Exchange に保存された自分の連絡先を取得できます。 移行が完了した時点でユーザーが Lync 2013 にログオンしている場合は、メッセージボックスが表示され、Lync からログオフするように求められ、処理を完了するために再びログオンするように求められます。 このユーザーごとのポリシーが割り当てられていないユーザーの連絡先は、統合連絡先ストアに移行されません。 これは、それらのユーザーがグローバルポリシーによって管理されており、グローバルポリシーで統合連絡先ストアの使用が無効にされているためです。

Lync Server 管理シェルで[test-csunifiedcontactstore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)コマンドレットを実行することにより、ユーザーの連絡先が統合連絡先ストアに正常に移行されたことを確認できます。

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

Test-CsUnifiedContactStore が成功すれば、統合連絡先ストアへのユーザー sip:kenmyer@litwareinc.com の連絡先の移行は完了しています。

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a>統合連絡先ストアのロールバック

ユーザーの連絡先を統合連絡先ストアから削除する必要がある場合 (たとえば、Microsoft Lync Server 2010 上でユーザーがホームポイントを設定する必要があり、そのため統合連絡先ストアを使用できなくなる場合) は、2つのことを行う必要があります。 最初に、ユーザーに新しいユーザーサービスポリシーを割り当てて、統合連絡先ストアに連絡先を保存することを禁止する必要があります。 (つまり、UcsAllowed プロパティが $False に設定されているポリシー)。このようなポリシーがない場合は、次のようなコマンドを使用して作成できます。

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

その後、次のようなコマンドを使用して、この新しいユーザーごとのポリシー (NoUnifiedContactStore) を割り当てます。

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

上記のコマンドは、ユーザー Ken Myer に新しいポリシーを割り当てると共に、Ken の連絡先が統合連絡先ストアに移行されないようにします。

<div>


> [!NOTE]  
> 場合によっては、単純にユーザーの現在のユーザー サービス ポリシーを割り当て解除するだけで同じ結果が得られます。たとえば、統合連絡先ストアを有効にするユーザーごとのユーザー サービス ポリシーが Ken Myer に割り当てられているが、グローバル ポリシーでは統合連絡先ストアの使用が禁止されているとします。その場合は、Ken のユーザーごとのサービス ポリシーを割り当て解除します。それにより、Ken は自動的にグローバル ポリシーによって管理されるようになるため、統合連絡先ストアにはアクセスできなくなります。<BR>以前に割り当てたユーザーごとのポリシーを割り当て解除するには、上記と同じコマンドを使用しますが、PolicyName パラメーターを null 値に設定します。<BR>Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null



</div>

統合連絡先ストアを操作する際には、"Ken の連絡先が統合連絡先ストアに移行されないようにする" という点に注意することが重要です。 単純に新しいユーザー サービス ポリシーを Ken に割り当てるだけでは、Ken の連絡先は統合連絡先ストアから移動されません。 ユーザーが Lync Server 2013 にログオンすると、システムはユーザーのユーザーサービスポリシーをチェックして、その連絡先を統合連絡先ストアに保持する必要があるかどうかを確認します。 答えが「はい」である (つまり、UcsAllowed プロパティが $True に設定されている) 場合は、連絡先が統合連絡先ストアに移行されます (連絡先がまだ統合連絡先ストアに移動されていないと仮定します)。 応答が [いいえ] の場合、Lync Server は単にユーザーの連絡先を無視し、次のタスクに進みます。 つまり、Lync Server は、UcsAllowed プロパティの値に関係なく、ユーザーの連絡先を統合連絡先ストアから自動的に移動することはありません。

これはつまり、ユーザーに新しいユーザーサービスポリシーを割り当てた後に、 [invoke-csucsrollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)コマンドレットを実行して、ユーザーの連絡先を Exchange 2013 から Lync Server 2013 に移行する必要があることも意味します。 たとえば、Ken Myer に新しいユーザー サービス ポリシーを割り当てた後、次のコマンドを使用して Ken の連絡先を統合連絡先ストアから移動できます。

    Invoke-CsUcsRollback -Identity "Ken Myer"

ユーザーサービスポリシーを変更しても、Invoke-csucsrollback コマンドレットを実行しない場合、Ken の連絡先は統合連絡先ストアから削除されません。 Invoke-csucsrollback を実行しても Ken Myer のユーザーサービスポリシーを変更しない場合はどうなりますか? その場合、Ken の連絡先が統合連絡先ストアから一時的に削除されます。 この削除が一時的なものであることを念頭に置いておくことが重要です。 Ken の連絡先が統合連絡先ストアから削除された後、Lync Server 2013 は7日待機してから、Ken に割り当てられているユーザーサービスポリシーを確認します。 統合連絡先ストアのユーザーを有効にするポリシーが Ken にまだ割り当てられている場合、その連絡先は自動的に連絡先ストアに戻されます。 統合連絡先ストアから連絡先を完全に削除するには、Invoke-csucsrollback コマンドレットを実行することに加えて、ユーザーサービスポリシーを変更する必要があります。

移行に影響を与える可能性がある大量の変数があるため、アカウントが統合連絡先ストアに完全に移行されるまでにかかる時間を予測するのは困難です。 ただし、一般的な規則として、少ない数の連絡先を移行する場合でも、移行が完了するまでに10分以上かかる場合があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

