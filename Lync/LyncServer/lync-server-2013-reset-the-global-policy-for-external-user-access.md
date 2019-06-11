---
title: 'Lync Server 2013: 外部ユーザー アクセスに関するグローバル ポリシーのリセット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 327a658bcd75c05e291798598e53947b23c0c12f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 での外部ユーザー アクセスに関するグローバル ポリシーのリセット

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-22_

グローバルポリシーを完全に削除することはできません。 グローバルポリシーの [**削除**] オプションを使うと、グローバルポリシーは既定の設定にリセットされます。これには、外部ユーザーアクセスオプションのサポートは含まれません。

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>グローバルポリシーを既定の設定にリセットするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**]、[**外部アクセスポリシー**] の順番にクリックします。

4.  [**外部アクセスポリシー** ] タブで、グローバルポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。

5.  削除を確認するメッセージが表示されたら、[ **OK**] をクリックします。 ページの上部に、グローバルポリシーがリセットされたことを通知するメッセージが表示されます。

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してグローバル外部アクセスポリシーをリセットする

グローバル外部アクセスポリシーをリセットするには、Windows PowerShell と CsExternalAccessPolicy コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 Management Shell またはリモートセッション Windows PowerShell から実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-reset-the-global-external-access-policy"></a>グローバル外部アクセスポリシーをリセットするには

  - このコマンドは、グローバル外部アクセスポリシーをリセットします。
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

詳細については、 [CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

