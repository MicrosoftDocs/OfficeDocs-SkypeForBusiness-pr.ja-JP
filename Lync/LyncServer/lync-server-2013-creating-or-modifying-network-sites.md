---
title: 'Lync Server 2013: ネットワークサイトの作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67d4fedf5931a85772e42a87fb80c382a364ae96
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a>Lync Server 2013 でのネットワークサイトの作成または変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-08_

ネットワーク サイトは、通話受付管理 (CAC) または Enhanced 9-1-1 展開の各地域内で構成されるオフィスまたは拠点です。 Microsoft Lync Server 2013 コントロールパネルを使用して、サイトを構成し、それらを地域に関連付けることができます。 たとえば、北アメリカのネットワーク地域は、シカゴ、レドモンド、バンクーバーなどのネットワーク サイトと関連付けられます。 CAC ネットワーク サイトは、サイトに帯域幅制限がない場合でも、組織内の各サイトに作成する必要があります。 Lync Server コントロールパネルから、ネットワークサイトの作成、変更、および削除を行うことができます。 ネットワーク サイトを作成または変更するには、以下の手順を使用します。 既存のネットワークサイトの削除の詳細については、「 [Lync Server 2013 での既存のネットワークサイトの削除](lync-server-2013-deleting-an-existing-network-site.md)」を参照してください。

<div>

## <a name="to-create-a-network-site"></a>ネットワーク サイトを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。

4.  [**サイト**] ページで、[**新規**] をクリックします。

5.  [**新しいサイト**] で、[**名前**] フィールドにサイトの名前を入力します。
    
    <div>
    

    > [!NOTE]  
    > サイト名は、Lync Server 2013 展開内で一意である必要があります。

    
    </div>

6.  [**地域**] ドロップダウン リストで、このサイトに関連付けるネットワーク地域を選択します。

7.  (オプション) このサイトに対する音声またはビデオ通話に帯域幅制限を設定する場合は、[**帯域幅ポリシー**] ドロップダウン リストで該当する設定値を備える帯域幅ポリシー プロファイルを選択します。
    
    <div>
    

    > [!NOTE]  
    > [<STRONG>ネットワーク構成</STRONG>] グループの [<STRONG>ポリシーのプロファイル</STRONG>] ページでは、利用可能な帯域幅ポリシー プロファイルの詳細を表示したり、新しい帯域幅ポリシー プロファイルを作成したりできます。 詳細については、「 <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Lync Server 2013 での帯域幅ポリシープロファイルの作成または変更</A>」を参照してください。

    
    </div>

8.  (オプション) このサイトに、場所に関する設定を提供する場合は、[**場所のポリシー**] ドロップダウン リストで場所のポリシーを選択します。
    
    <div>
    

    > [!NOTE]  
    > 場所のポリシーは、特定の Enhanced 9-1-1 (E9-1-1) とクライアントの場所に関連する設定をサイトに割り当てます。 [<STRONG>ネットワーク構成</STRONG>] グループの [<STRONG>場所のポリシー</STRONG>] ページでは、利用可能な場所のポリシーの詳細を表示したり、新しい場所のポリシーを作成したりできます。 詳細については、「 <A href="lync-server-2013-viewing-location-policy-information.md">Lync Server 2013 で場所ポリシー情報を表示</A>する」を参照してください。

    
    </div>

9.  (オプション) [**説明**] フィールドに値を入力して、名前だけでは表現することのできないこのサイトの詳細情報を提供します。

10. [**確定**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 新しいネットワーク サイトを作成するとき、[<STRONG>関連付けられたサブネット</STRONG>] テーブルは使用しません。 サブネットの作成または変更時に、サブネットをサイトに関連付けます。 詳細については、「 <A href="lync-server-2013-create-or-modify-network-subnets.md">Lync Server 2013 でネットワークサブネットを作成または変更する</A>」を参照してください。

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a>ネットワーク サイトを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。

4.  [**サイト**] ページで、変更するサイトをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**サイトの編集**] ページでは、サイトに関連付けられた、説明、地域、帯域幅ポリシー プロファイル、および場所のポリシーを変更できます。詳細については、このトピックの「ネットワーク サイトを作成するには」を参照してください。

7.  [**確定**] をクリックします。

このページの [**関連付けられたサブネット**] テーブルを変更することはできません。 関連付けられたサブネットの一覧は、参照のために用意されており、サイトの設定を変えるとどのサブネットが影響を受けるかを確認できます。

</div>

<div>

## <a name="to-delete-a-network-site"></a>ネットワーク サイトを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。

4.  [**サイト**] ページで、削除するサイトをクリックします。
    
    <div>
    

    > [!NOTE]  
    > 1 つ以上のサイトを一度に削除できます。 これを実行するには、Ctrl キーを押しながら、複数のサイトを選択します。 また、すべてのサイトを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。

    
    </div>

5.  [**編集**] メニューの [**削除**] をクリックします。

6.  [**OK**] をクリックします。
    
    <div>
    

    > [!WARNING]  
    > ただし、ネットワーク サイトがネットワーク サブネットに関連付けられている場合は、サイトを削除することはできません。 サブネットに関連付けられているサイトを削除しようとすると、エラー メッセージが表示されます。 サイトがサブネットに関連付けられているかどうかを確認するには、そのサイトをクリックして、[<STRONG>編集</STRONG>] メニューの [<STRONG>詳細の表示</STRONG>] をクリックします。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での既存のネットワークサイトの削除](lync-server-2013-deleting-an-existing-network-site.md)  


[新しい-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[設定-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[-CsNetworkSite の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[-CsNetworkSite の取得](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

