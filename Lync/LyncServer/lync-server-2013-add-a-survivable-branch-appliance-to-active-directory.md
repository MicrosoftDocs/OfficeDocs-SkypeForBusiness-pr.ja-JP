---
title: 'Lync Server 2013: 存続可能 Branch Appliance を Active Directory に追加する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da38ead0e1d27ef1024d8aac2ea030d2815e6cad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a>Lync Server 2013 で存続可能 Branch Appliance を Active Directory に追加する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-23_

存続可能ブランチアプライアンスを展開することを計画している場合は、存続可能 Branch Appliance を Active Directory ドメインサービスに追加する必要があります。 中央サイトでこの手順を実行します。

<div>


> [!IMPORTANT]  
> この手順は、存続可能ブランチアプライアンスを展開している場合にのみ実行してください。 存続可能ブランチサーバーを展開している場合は、この操作を実行しないでください。



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a>存続可能ブランチ アプライアンスを Active Directory ドメイン サービスに追加するには

1.  Enterprise Admins グループのメンバーとしてメンバー サーバーにログオンします。

2.  [**スタート**]、[**管理ツール**]、[**Active Directory ユーザーとコンピューター**] の順にクリックします。

3.  [**操作**] メニューの [**新規**] をクリックし、[**コンピューター**] をクリックします。

4.  [**新しいオブジェクト-コンピューター** ] ダイアログボックスで、存続可能 Branch Appliance のコンピューターオブジェクトの名前 (たとえば、BranchOffice1) を入力し、[**変更**] をクリックします。

5.  [**ユーザーまたはグループの選択**] ダイアログ ボックスで、RTCUniversalSBATechnicians グループを追加して [**OK**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > ブランチ サイトの RTCUniversalSBATechnicians グループのメンバーが、後でこのデバイスをドメインに追加します。

    
    </div>

6.  [ **OK]** をクリックして、存続可能 Branch Appliance コンピューターオブジェクトを保存します。

7.  [**スタート**]、[**管理ツール**]、[**ADSI Edit**] の順にクリックします。

8.  [**ADSI Edit**] で、前のステップで作成したコンピューター オブジェクトを右クリックし、[**プロパティ**] をクリックします。

9.  属性リストで **servicePrincipalName** をクリックし、[**編集**] をクリックします。

10. [**追加する値**] フィールドに「HOST/\<SBA FQDN\> 」 \<と入力\>します。 SBA fqdn は、存続可能 Branch Appliance の完全修飾ドメイン名 (fqdn) です。 たとえば、「 **HOST/BranchOffice1**」と入力します。

11. [**OK**] をクリックして **servicePrincipalName** 属性の設定を保存し、[**OK**] をクリックしてコンピューター オブジェクトのプロパティを保存します。

12. [**Active Directory ユーザーとコンピューター**] で [**ユーザー**] を右クリックし、[**新規作成**] をクリックして [**ユーザー**] をクリックします。

13. ウィザードに情報を入力して、存続可能 Branch Appliance 技術者のドメインユーザーアカウントを作成します。

14. [**Active Directory ユーザーとコンピューター**] で [**ユーザー**] をクリックし、ユーザー オブジェクトを右クリックして [**グループに追加**] をクリックします。

15. [**選択するオブジェクト名を入力してください**] に **RTCUniversalSBATechnicians** と入力し、[**OK**] をクリックします。

16. ブランチ サイト技術者ごとに、ステップ 12 ～ 15 を繰り返します。

**次のステップ**: [Lync Server 2013 でのトポロジへのブランチサイトの追加](lync-server-2013-add-branch-sites-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

