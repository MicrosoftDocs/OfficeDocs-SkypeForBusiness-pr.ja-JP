---
title: 'Lync Server 2013: 会議参加ページの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a62ac96688887e9d5ee66f0f0439a73941db3563
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a>Lync Server 2013 での会議参加ページの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-12-14_

ユーザーが会議出席依頼の会議リンクをクリックすると、会議参加ページによって、ユーザーのコンピューターに Lync 2013 クライアントが既にインストールされているかどうかが検出されます。 クライアントがすでにインストールされている場合、クライアントがミーティングを開き、参加します。 クライアントがインストールされていない場合、既定では、2013バージョンの Lync Web App が開きます。

ユーザーが Office Communicator 2007 R2 または Lync 2010 アテンダントを使用して会議に参加できるようにする場合は、会議参加ページの動作を変更することができます。 これらの構成オプションは Lync Server 2013 コントロールパネルから削除されましたが、Set-cswebserviceconfiguration コマンドレットを使用して構成します。

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a>ミーティング参加ページの Set-CsWebServiceConfiguration パラメーター

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Set-CsWebServiceConfiguration パラメーター</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>True に設定すると、Lync 以外のクライアントアプリケーションを使用して会議に参加しているユーザーには、Office Communicator 2007 R2 を使用して会議に参加する機会が与えられます。 既定値は False です。</p></td>
</tr>
<tr class="even">
<td><p>Showalternatejoinoptionsexpan</p></td>
<td><p>True に設定した場合、オンライン会議に参加するための別のオプション (Office Communicator 2007 R2 など) が自動的に展開され、ユーザーに表示されます。False (既定値) に設定されている場合、これらのオプションは使用可能ですが、ユーザーが自分でオプションの一覧を表示する必要があります。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>Lync Server 2013 管理シェルを使用して会議参加ページを構成するには

1.  Lync Server 2013 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  Web サービス構成設定を表示するには、次のコマンドレットを実行します。
    
        Get-CsWebServiceConfiguration

3.  ユーザーの設定に応じて、パラメーターを True または False に設定して、次のコマンドを実行します (このコマンドレットのパラメーターの詳細については、「 [set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) In Lync Server 2013 Management Shell documentation」を参照してください)。
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a>関連項目


[Set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

