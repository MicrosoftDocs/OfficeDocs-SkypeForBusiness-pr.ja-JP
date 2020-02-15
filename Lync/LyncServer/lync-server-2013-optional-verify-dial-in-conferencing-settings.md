---
title: 'Lync Server 2013: (オプション) ダイヤルイン会議の設定の検証'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86ec4e4852594e7e4748213de994b6b4f471d460
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a>オプションLync Server 2013 でダイヤルイン会議の設定を確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2010-11-02_

ダイヤルイン会議構成の最後の確認作業として、どのアクセス番号も使用しないダイヤルイン会議の地域があるダイヤル プランやダイヤルイン会議の地域が指定されていないアクセス番号を検索します。このステップはオプションです。

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>どのアクセス番号も使用しないダイヤルイン会議の地域があるダイヤル プランを検索するには

1.  RTCUniversalServerAdmins グループのメンバーか、**Cs-ServerAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  コマンド プロンプトで次のコマンドを実行します。
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    このコマンドレットは、どのアクセス番号も使用していないダイヤルイン会議の地域がある、すべてのダイヤル プランを返します。

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a>地域が割り当てられていないアクセス番号を検索するには

1.  RTCUniversalServerAdmins グループのメンバーか、**Cs-ServerAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  コマンド プロンプトで次のコマンドを実行します。
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    このコマンドレットは、地域に関連付けられていないダイヤルイン会議のアクセス番号をすべて返します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

