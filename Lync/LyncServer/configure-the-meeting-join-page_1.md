---
title: 会議参加ページの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure the meeting join page
ms:assetid: a87319b7-3124-4262-8f9d-18138870ee2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205145(v=OCS.15)
ms:contentKeyID: 48185030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07c3797f62fb1d6b7df0274d26fb1ddde706a66a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a>会議参加ページの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-12-14_

ユーザーが会議出席依頼の会議リンクをクリックすると、[会議の参加] ページによって、ユーザーのコンピューターに Lync 2013 クライアントが既にインストールされているかどうかが検出されます。 クライアントが既にインストールされている場合は、そのクライアントが開き、会議に参加します。 クライアントがインストールされていない場合、既定では、2013バージョンの Microsoft Lync Web App が開きます。

ユーザーが Office Communicator 2007 R2 または Lync 2010 アテンダントを使って会議に参加できるようにする場合は、[会議参加] ページの動作を変更することができます。 これらの構成オプションは、Lync Server 2013 コントロールパネルから削除されていますが、CsWebServiceConfiguration コマンドレットを使用して設定します。

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a>会議の参加ページの CsWebServiceConfiguration パラメーター

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>CsWebServiceConfiguration パラメーター</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>True に設定すると、Lync 以外のクライアントアプリケーションを使用して会議に参加するユーザーには、Office Communicator 2007 R2 を使用して会議に参加する機会が与えられます。 既定値は False です。</p></td>
</tr>
<tr class="even">
<td><p>Showalternatejoinoptionている</p></td>
<td><p>True に設定すると、オンライン会議に参加するための代替オプション (Office Communicator 2007 R2 など) が自動的に展開され、ユーザーに表示されます。 False (既定値) に設定した場合、これらのオプションは使用できますが、ユーザーは自分のオプションの一覧を表示する必要があります。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>Lync Server 2013 管理シェルを使用して会議の参加ページを構成するには

1.  Lync Server 2013 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  次のコマンドレットを実行します。
    
        Get-CsWebServiceConfiguration
    
    このコマンドレットは、web サービスの構成設定を返します。

3.  次のコマンドを実行します。設定に応じてパラメーターが True または False に設定されています (このコマンドレットのパラメーターの詳細については、「Lync Server 2013 管理シェルドキュメント」を参照してください)。
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

