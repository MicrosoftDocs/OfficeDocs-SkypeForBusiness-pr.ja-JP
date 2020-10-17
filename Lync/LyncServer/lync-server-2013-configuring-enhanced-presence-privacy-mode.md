---
title: 'Lync Server 2013: 拡張プレゼンスプライバシーモードの構成'
description: 'Lync Server 2013: 拡張プレゼンスプライバシーモードの構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8eab347d233c23a9a4becf119dee673d3021dfa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548453"
---
# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>Lync Server 2013 での拡張プレゼンスプライバシーモードの構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-12-08_

拡張プレゼンスプライバシーモードを使用すると、ユーザーは自分のプレゼンス情報を制限して、Lync 2013 の連絡先リストに記載されている連絡先のみが表示されるようにすることができます。 **Get-csprivacyconfiguration 戻し**   および**get-csprivacyconfiguration 戻し**コマンドレットでは、このオプションを制御する enableprivacymode パラメーターが設定されています。 EnablePrivacyMode が True に設定されている場合は、連絡先にプレゼンス情報を制限するオプションが Lync 2013 ステータスオプションで利用可能になります。 EnablePrivacyMode が False に設定されている場合は、ユーザーがすべてのユーザーに対して自身のプレゼンス情報を常に表示できるようにするか、あるいは管理者がプライバシー モードに加える今後の変更に従うかのどちらかを選択できます。

<div>


> [!IMPORTANT]  
> Lync 2013 および Lync 2010 のプライバシー設定は、以前のバージョンでは受け入れられません (Microsoft Office Communicator 2007 R2 または Microsoft Office Communicator 2007)。 以前のバージョンの Office Communicator でサインインが許可されている場合は、表示が許可されていないユーザーが Lync 2013 ユーザーの状態、連絡先情報、または画像を表示することができます。 また、Lync 2013 ユーザーのプライバシー設定は、後で以前のバージョンの Communicator を使用してサインインした場合にリセットされます。<BR>これらの理由から、移行シナリオでは、拡張プレゼンス プライバシー モードを有効にする前に、以下のことを実行してください。 
> <UL>
> <LI>
> <P>すべてのユーザーに Lync 2013 がインストールされていることを確認します。</P>
> <LI>
> <P>Communicator の以前のバージョンによるサインインを回避する、クライアント バージョンのポリシー ルールを定義します。</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>拡張プレゼンス プライバシー モードを有効にするには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  次のコマンドを実行します。
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    このコマンドによって、組織で現在使用されているすべてのプライバシー構成設定のプライバシー モードが有効になります。 Lync Server 拡張プレゼンスプライバシーモードのポリシー構成が Lync 2013 クライアントの連絡先プレゼンスを管理する方法の詳細については、Microsoft サポート技術情報の記事「 [Lync server enhanced プレゼンスプライバシーモードを有効にする」を参照してください。一部の lync 連絡先のプレゼンス状態が "利用不可" に更新](https://support.microsoft.com/kb/3020057)されます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-csprivacyconfiguration 戻し](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[Get-csprivacyconfiguration 戻し](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[Get-csprivacyconfiguration 戻し](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

