---
title: 'Lync Server 2013: 拡張プレゼンスプライバシーモードを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 878691cd7b39d893b416a128f937d2aad1e561b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>Lync Server 2013 で拡張プレゼンスプライバシーモードを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-12-08_

強化されたプレゼンスプライバシーモードでは、ユーザーは自分のプレゼンス情報を、Lync 2013 の連絡先リストに記載されている連絡先だけに表示されるように制限することができます。 **CsPrivacyConfiguration** と**CsPrivacyConfiguration**コマンドレットには、このオプションを制御する enableprivacymode パラメーターがあります。 EnablePrivacyMode が True に設定されている場合、連絡先にプレゼンス情報を制限するオプションは Lync 2013 の [状態] オプションで利用可能になります。 EnablePrivacyMode が False に設定されている場合、ユーザーは自分のプレゼンス情報の表示を常に許可するか、管理者がプライバシーモードに加えた将来の変更に従うかを選ぶことができます。

<div>


> [!IMPORTANT]  
> Lync 2013 および Lync 2010 のプライバシー設定は、以前のバージョン (Microsoft Office Communicator 2007 R2 または Microsoft Office Communicator 2007) には有効ではありません。 以前のバージョンの Office Communicator でサインインが許可されている場合、Lync 2013 ユーザーの状態、連絡先情報、または画像を表示する権限が与えられていないユーザーは写真を表示できます。 さらに、後で以前のバージョンの Communicator でサインインした場合は、Lync 2013 ユーザーのプライバシー設定がリセットされます。<BR>これらの理由から、拡張プレゼンスプライバシーモードを有効にする前に、移行シナリオで次のようにします。 
> <UL>
> <LI>
> <P>すべてのユーザーに Lync 2013 がインストールされていることを確認します。</P>
> <LI>
> <P>以前のバージョンの Communicator でサインインできないように、クライアントのバージョンポリシールールを定義します。</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>拡張プレゼンスプライバシーモードを有効にするには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  次のコマンドを実行します。
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    このコマンドにより、組織で現在使用されているすべてのプライバシー構成設定のプライバシーモードが有効になります。 Lync Server 拡張プレゼンスプライバシーモードのポリシー構成で Lync 2013 クライアントの連絡先プレゼンスを管理する方法の詳細については、Microsoft サポート技術情報の記事「Lync Server の拡張された[プレゼンスプライバシーモードの更新」を参照してください。一部の Lync 連絡先の状態が [利用不可] になっ](http://support.microsoft.com/kb/3020057)ています。

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[新規-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

