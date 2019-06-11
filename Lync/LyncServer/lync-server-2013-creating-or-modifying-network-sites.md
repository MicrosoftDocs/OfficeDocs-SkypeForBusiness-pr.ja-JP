---
title: 'Lync Server 2013: ネットワークサイトの作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bb09dfcd490d47de1bbfbbde48f538e95fc64cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a>Lync Server 2013 でのネットワークサイトの作成または変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-08_

[ネットワークサイト] は、通話受付制御 (CAC) または拡張9-1-1 展開の各領域内に構成されているオフィスまたは場所です。 Microsoft Lync Server 2013 コントロールパネルを使用して、サイトを構成し、それらを地域と関連付けることができます。 たとえば、北米向けのネットワーク領域は、シカゴ、Redmond、バンクーバーなどのネットワークサイトに関連付けられている場合があります。 サイト内のすべてのサイトに対して、CAC ネットワークサイトを作成する必要があります。このサイトには帯域幅の制限がありません。 Lync Server コントロールパネルからネットワークサイトの作成、変更、削除を行うことができます。 ネットワークサイトを作成または変更するには、次の手順を使用します。 既存のネットワークサイトを削除する方法について詳しくは、「 [Lync Server 2013 で既存のネットワークサイトを削除する](lync-server-2013-deleting-an-existing-network-site.md)」をご覧ください。

<div>

## <a name="to-create-a-network-site"></a>ネットワークサイトを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。

4.  [**サイト**] ページで、[**新規**] をクリックします。

5.  [**新しいサイト**] の [**名前**] フィールドに、このサイトの名前を入力します。
    
    <div>
    

    > [!NOTE]  
    > サイト名は、Lync Server 2013 の展開内で一意である必要があります。

    
    </div>

6.  [ **Region** ] ドロップダウンリストで、このサイトに関連付けるネットワーク領域を選びます。

7.  省略このサイトへの音声通話またはビデオ通話に帯域幅の制限を設定する場合は、[**帯域幅ポリシー** ] ドロップダウンリストから適切な設定を使用して、帯域幅ポリシーのプロファイルを選択します。
    
    <div>
    

    > [!NOTE]  
    > 利用可能な帯域幅ポリシープロファイルの詳細を表示したり、新しい帯域幅ポリシープロファイルを作成したりするには、[<STRONG>ネットワーク構成</STRONG>] グループの [<STRONG>ポリシープロファイル</STRONG>] ページを使用します。 詳細について<A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">は、「Lync Server 2013 で帯域幅ポリシープロファイルを作成または変更する</A>」を参照してください。

    
    </div>

8.  省略このサイトの場所の設定を指定する場合は、[**場所のポリシー** ] ドロップダウンリストから場所のポリシーを選びます。
    
    <div>
    

    > [!NOTE]  
    > 位置情報ポリシーは、特定の拡張 9-1-1 (E9) およびクライアントの場所の設定をサイトに割り当てます。 利用可能な位置情報ポリシーの詳細を表示するか、[<STRONG>ネットワーク構成</STRONG>] グループの [<STRONG>場所のポリシー</STRONG> ] ページから新しい場所ポリシーを作成することができます。 詳細については、「 <A href="lync-server-2013-viewing-location-policy-information.md">Lync Server 2013 で位置情報ポリシー情報を表示</A>する」を参照してください。

    
    </div>

9.  省略[**説明**] フィールドに値を入力して、このサイトについて、名前だけでは表現できない詳細情報を入力します。

10. [**コミット**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 新しいネットワークサイトを作成する場合は、<STRONG>関連するサブネット</STRONG>テーブルを使用しません。 サブネットを作成または変更するときに、サブネットをサイトに関連付けます。 詳細については、「 <A href="lync-server-2013-create-or-modify-network-subnets.md">Lync Server 2013 でネットワークサブネットを作成または変更する</A>」を参照してください。

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a>ネットワークサイトを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。

4.  [**サイト**] ページで、変更するサイトをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**サイトの編集**] ページでは、サイトに関連付けられている説明、地域、帯域幅ポリシーのプロファイル、および場所のポリシーを変更できます。 詳細については、このトピックの前半の「ネットワークサイトを作成する」セクションを参照してください。

7.  [**コミット**] をクリックします。

このページでは、**関連するサブネット**テーブルを変更することはできません。 関連付けられたサブネットの一覧は参照用に提供されるため、サイトの設定を変更したときに影響を受けるサブネットを認識できます。

</div>

<div>

## <a name="to-delete-a-network-site"></a>ネットワークサイトを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。

4.  [**サイト**] ページで、削除するサイトをクリックします。
    
    <div>
    

    > [!NOTE]  
    > 一度に複数のサイトを削除できます。 この操作を行うには、ctrl キーを押しながら複数のサイトを選び、CTRL キーを押しながら選択します。 または、すべてのサイトを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。

    
    </div>

5.  [**編集**] メニューの [**削除**] をクリックします。

6.  **[OK]** をクリックします。
    
    <div>
    

    > [!WARNING]  
    > ネットワークサイトがネットワークサブネットに関連付けられている場合は、そのサイトを削除することはできません。 サブネットに関連付けられているサイトを削除しようとすると、エラーメッセージが表示されます。 サイトがいずれかのサブネットに関連付けられているかどうかを確認するには、サイトをクリックし、[<STRONG>編集</STRONG>] メニューの [<STRONG>詳細の表示</STRONG>] をクリックします。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で既存のネットワークサイトを削除する](lync-server-2013-deleting-an-existing-network-site.md)  


[新しい-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[CsNetworkSite の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

