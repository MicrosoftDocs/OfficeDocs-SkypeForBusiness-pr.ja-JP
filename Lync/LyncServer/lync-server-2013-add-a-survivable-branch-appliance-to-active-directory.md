---
title: 'Lync Server 2013: Active Directory への存続可能ブランチ アプライアンスの追加'
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
ms.openlocfilehash: 8712dcb5b68522a8b770aac63c5a37a1a70a669a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a>Lync Server 2013 での、Active Directory への存続可能ブランチ アプライアンスの追加

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-23_

Survivable Branch Appliance の展開を計画している場合は、Survivable Branch Appliance を Active Directory ドメインサービスに追加する必要があります。 セントラルサイトでこの手順を実行します。

<div>


> [!IMPORTANT]  
> この手順は、Survivable Branch Appliance を展開している場合にのみ実行してください。 Survivable ブランチサーバーを展開する場合は、この操作を行わないでください。



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a>Active Directory ドメインサービスに Survivable Branch アプライアンスを追加するには

1.  Enterprise Admins グループのメンバーとしてメンバーサーバーにログオンします。

2.  [**スタート**] をクリックし、[**管理ツール**] をクリックして、[ **Active Directory ユーザーとコンピューター**] をクリックします。

3.  [**操作**] メニューの [**新規作成**] をクリックし、[**コンピューター**] をクリックします。

4.  [**新しいオブジェクト-コンピューター** ] ダイアログボックスで、Survivable Branch アプライアンスのコンピューターオブジェクトの名前 (たとえば BranchOffice1) を入力し、[**変更**] をクリックします。

5.  **[ユーザーまたはグループの選択**] ダイアログボックスで、RTCUniversalSBATechnicians グループを追加し、[ **OK]** をクリックします。
    
    <div>
    

    > [!NOTE]  
    > ブランチサイトの RTCUniversalSBATechnicians グループのメンバーは、このデバイスを後でドメインに追加します。

    
    </div>

6.  [ **OK** ] をクリックして、Survivable Branch Appliance コンピューターオブジェクトを保存します。

7.  [**スタート**] をクリックし、[**管理ツール**] をクリックして、[ **ADSI の編集**] をクリックします。

8.  **ADSI edit**で、前の手順で作成したコンピューターオブジェクトを右クリックし、[**プロパティ**] をクリックします。

9.  [属性] の一覧で、[ **servicePrincipalName**] をクリックし、[**編集**] をクリックします。

10. [**追加する値**] フィールドに、「HOST\</SBA\> fqdn \<」と\>入力します。 SBA fqdn は Survivable Branch Appliance の完全修飾ドメイン名 (FQDN) です。 たとえば、「 **HOST/BranchOffice1**」と入力します。

11. [ **Ok** ] をクリックして**servicePrincipalName**属性の設定を保存してから、[ **ok** ] をクリックして、コンピューターオブジェクトのプロパティを保存します。

12. **Active Directory ユーザーとコンピューター**で、[**ユーザー**] を右クリックし、[**新規作成**] をクリックして、[**ユーザー**] をクリックします。

13. ウィザードに情報を入力して、Survivable Branch Appliance テクニシャンのドメインユーザーアカウントを作成します。

14. [ **Active Directory ユーザーとコンピューター**] で [**ユーザー**] をクリックし、ユーザーオブジェクトを右クリックして、[**グループに追加**] をクリックします。

15. **[選択するオブジェクト名を入力**してください] に「 **RTCUniversalSBATechnicians**」と入力して、[ **OK]** をクリックします。

16. ブランチサイトの技術ごとに、手順12-15 を繰り返します。

**次のステップ**: [Lync Server 2013 でトポロジにブランチサイトを追加する](lync-server-2013-add-branch-sites-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

