---
title: 'Lync Server 2013: アーカイブのグローバルポリシーを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ccb5ba267c3dc94e14f00cf96f240fa2f0e91b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a>Lync Server 2013 でアーカイブ用のグローバルポリシーを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-09_

フロントエンドサーバーを展開すると、Lync Server によってアーカイブ用のグローバルポリシーが作成されます。 既定では、アーカイブはグローバルポリシーで無効になっています。 グローバルポリシーは、サイトまたはユーザーのポリシーをセットアップしてグローバルポリシーを上書きするか、または Microsoft Exchange の統合を使用しているかどうかにかかわらず、展開全体の内部と外部の通信でアーカイブを有効にするかどうかを制御します。ユーザー。 Microsoft Exchange 統合を使用している場合、グローバルポリシーは、Exchange 2013 を使用していて、メールボックスがインプレースホールドに配置されているユーザーには適用されません。

グローバル、サイト、ユーザーのポリシーの階層など、アーカイブポリシーの動作について詳しくは、「 [Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)」をご覧ください。

<div>


> [!NOTE]  
> 展開で Microsoft Exchange の統合を有効にした場合、exchange 2013 を使っているユーザーに対してアーカイブが有効になっていて、メールボックスがインプレースホールドに配置されているかどうかを Exchange のインプレースホールドポリシーで制御します。 詳細については、展開ドキュメントで<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server との統合を使用する場合の「Lync server 2013 でアーカイブするためのポリシーを設定する</A>」を参照してください。<BR>アーカイブを有効にする前に、アーカイブ構成ですべての適切なオプションを指定する必要があります。 詳細については、展開ドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 でアーカイブオプションを構成する</A>」を参照してください。



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a>Lync Server アーカイブデータベースを使用するときに、アーカイブ用のグローバルポリシーを構成するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。 Lync Server 2013 コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。

4.  [**アーカイブ ポリシー**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] をクリックします。

5.  [**アーカイブ ポリシーの編集 - グローバル**] で、以下の手順を実行します。
    
      - "グローバル" という既定の名前を使用しない場合は、[**名前**] にグローバル ポリシーの新しい名前を指定します。
    
      - [**説明**] に、そのポリシーの内容に関する情報を入力します (たとえば、「**<部署名> のグローバル ポリシー」など)。
    
      - サイト ポリシーまたはユーザー ポリシーによって特に制御されていないすべてのサイトとユーザーの内部通信のアーカイブを制御するには、[**内部通信のアーカイブ**] チェック ボックスをオンまたはオフにします。
    
      - サイト ポリシーまたはユーザー ポリシーによって特に制御されていないすべてのサイトとユーザーの外部通信のアーカイブを制御するには、[**外部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。

6.  [**確定**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

