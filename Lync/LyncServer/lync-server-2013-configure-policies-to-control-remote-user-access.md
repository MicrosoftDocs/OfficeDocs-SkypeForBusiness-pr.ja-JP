---
title: 'Lync Server 2013: リモートユーザーアクセスを制御するポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f1687a26e5bf464191b742d046bc28e8c8a329a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a>Lync Server 2013 でのリモートユーザーアクセスを制御するポリシーの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-18_

1つ以上の外部ユーザーアクセスポリシーを構成して、リモートユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御します。 リモート ユーザー アクセスを管理するため、グローバル、サイト、およびユーザー レベルでポリシーを構成できます。 サイト ポリシーはグローバル ポリシーより優先され、ユーザー ポリシーはサイト ポリシーとグローバル ポリシーより優先されます。 構成できるポリシーの種類の詳細については、「 [Lync Server 2013 へのフェデレーションと外部アクセスの管理](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)」を参照してください。 あるポリシー レベルで適用されている Lync Server ポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。 Lync Server ポリシーの優先順位は、ユーザー ポリシーが最も高く、サイト ポリシー、グローバル ポリシー (優先度が最も低い) と続きます。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。

<div>


> [!NOTE]  
> 組織のリモート ユーザー アクセスを有効にしていない場合でも、リモート ユーザー アクセスを制御するポリシーを構成できます。 ただし、構成したポリシーは、組織のリモート ユーザー アクセスを有効にしているときのみ有効です。 リモートユーザーアクセスの有効化の詳細については、「 <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 のフェデレーションとパブリック IM 接続を有効または無効</A>にする」を参照してください。 また、リモートユーザーアクセスを制御するユーザーポリシーを指定した場合、このポリシーは、Lync Server が有効になっていて、そのポリシーを使用するように構成されているユーザーにのみ適用されます。 リモートの場所から Lync Server にサインインできるユーザーの指定の詳細については、「 <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Lync server 2013 で lync が有効なユーザーへの外部ユーザーアクセスポリシーの割り当て</A>」を参照してください。



</div>

リモート ユーザー アクセスの制御に使用する各外部アクセス ポリシーを構成するには、次の手順を使用します。

<div>


> [!NOTE]  
> この手順で説明するのは、リモート ユーザーとの通信を有効にするだけのポリシーを構成する方法ですが、リモート ユーザー アクセスをサポートするため構成する各ポリシーで、フェデレーション ユーザー アクセスやパブリック ユーザー アクセスも構成できます。 フェデレーションユーザーをサポートするようにポリシーを構成する方法の詳細については、「 <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でフェデレーションユーザーアクセスを制御するようにポリシーを構成する</A>」を参照してください。 パブリックユーザーをサポートするためのポリシーの構成の詳細については、「 <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013 でのパブリック SIP フェデレーションプロバイダーの作成または編集</A>」を参照してください。



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>リモート ユーザー アクセスをサポートする外部アクセス ポリシーを構成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。

4.  [**外部アクセス ポリシー**] ページで、次のいずれかの操作を行います。
    
      - リモート ユーザー アクセスをサポートするグローバル ポリシーを構成するには、グローバル ポリシーをクリックして [**編集**] をクリックし、[**詳細の表示**] をクリックします。
    
      - 新しいサイト ポリシーを作成するには、[**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。 [**サイトの選択**] で一覧から適切なサイトをクリックし、[**OK**] をクリックします。
    
      - 新しいユーザー ポリシーを作成するには、[**新規作成**] をクリックし、[**ユーザー ポリシー**] をクリックします。 [**新しい外部アクセス ポリシー**] の [**名前**] フィールドに、ユーザー ポリシーの範囲を示す一意の名前を作成します (リモート ユーザーの通信を有効にするユーザー ポリシーの場合は **EnableRemoteUsers** など)。
    
      - 既存のポリシーを変更するには、表に表示されている適切なポリシーをクリックし、[**編集**] に続いて [**詳細の表示**] をクリックします。

5.  (オプション) 説明を追加または編集する場合は、[**説明**] でポリシーの情報を指定します。

6.  次のどちらかの操作を行います。
    
      - ポリシーのリモート ユーザー アクセスを有効にするには、[**リモート ユーザーとの通信を有効にする**] チェック ボックスをオンにします。
    
      - ポリシーのリモート ユーザー アクセスを無効にするには、[**リモート ユーザーとの通信を有効にする**] チェック ボックスをオフにします。

7.  [**確定**] をクリックします。

リモート ユーザー アクセスを有効にするには、組織のリモート ユーザー アクセスのサポートも有効にする必要があります。 詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Lync Server 2013 でのフェデレーションとパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)」を参照してください。

これがユーザー ポリシーである場合は、リモート接続を許可するユーザーにポリシーを適用する必要もあります。 詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「lync [Server 2013 での lync が有効なユーザーへの外部ユーザーアクセスポリシーの割り当て](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

