---
title: 'Lync Server 2013: アーカイブ用のグローバルポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c31176581b1c34556a75b7fe039a06862249d397
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a>Lync Server 2013 でのアーカイブ用のグローバルポリシーの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-09_

フロントエンドサーバーを展開すると、Lync Server によってアーカイブ用のグローバルポリシーが作成されます。 既定では、グローバルポリシーでアーカイブは無効になっています。 グローバルポリシーでは、サイトポリシーまたはユーザーポリシーを設定してグローバルポリシーを上書きするか、または Microsoft Exchange 統合を使用して一部またはすべてのを展開する場合を除いて、展開全体の内部通信と外部通信のアーカイブを有効にするかどうかを制御します。ユーザー。 Microsoft Exchange 統合を使用する場合、グローバルポリシーは、Exchange 2013 に所属していて、メールボックスがインプレース保持に配置されているすべてのユーザーには適用されません。

グローバルポリシー、サイトポリシー、およびユーザーポリシーの階層を含むアーカイブポリシーのしくみの詳細については、「 [Lync Server 2013](lync-server-2013-how-archiving-works.md)の計画に関するドキュメント、展開に関するドキュメント、または操作のドキュメントでのアーカイブの仕組み」を参照してください。

<div>


> [!NOTE]  
> 展開に対して Microsoft Exchange 統合を有効にすると、exchange 2013 に所属しているユーザーに対してアーカイブを有効にし、メールボックスをインプレース保持に設定するかどうかを Exchange のインプレース保持ポリシーで制御します。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies For Exchange server integration using The Lync server 2013</A> 」を参照してください。<BR>アーカイブを有効にするには、その前にアーカイブ構成で適切なオプションをすべて指定する必要があります。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 のアーカイブオプションの構成</A>」を参照してください。



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a>Lync Server アーカイブ データベースを使用するときにアーカイブのグローバル ポリシーを構成するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。 Lync Server 2013 コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

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

