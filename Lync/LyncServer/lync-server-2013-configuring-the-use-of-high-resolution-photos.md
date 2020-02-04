---
title: 'Lync Server 2013: 高解像度の写真を使用するように構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cb82c047491a43f2a8682d3a6688f67e76af730
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a>Microsoft Lync Server 2013 で高解像度の写真を使用するように構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-05_

Microsoft Lync Server 2010 では、ユーザーが連絡先の写真を表示できるようになりました (および自分の写真を他のユーザーに公開する) ことができます。 通常、これらの写真は、ユーザーの thumbnailPhoto 属性の一部として Active Directory に保存されています。 写真のサイズと解像度には深刻な制限があります。 thumbnailPhoto 属性は、最大サイズが48ピクセル、48ピクセルの写真のみを保持できます。

ただし、Microsoft Lync Server 2013 では、ユーザーの Microsoft Exchange Server 2013 メールボックスに写真を保存できます。これにより、写真のサイズが最大648ピクセル、648ピクセルになります。 また、Exchange 2013 は、必要に応じて異なる製品で使用するために、これらの写真のサイズを自動的に変更することができます。 通常、3つの異なる写真のサイズと解像度を意味します。

  - 48ピクセル x 48 ピクセル、Active Directory thumbnailPhoto 属性に使用されているサイズ。 Exchange 2013 の Exchange に写真をアップロードすると、その写真の48ピクセルと48ピクセルのバージョンが自動的に作成され、ユーザーの thumbnailPhoto 属性が更新されます。 ただし、この逆のことはできないことに注意してください。 Active Directory の thumbnailPhoto 属性を手動で更新した場合、ユーザーの Exchange 2013 メールボックスの写真は自動的に更新されません。

  - 96ピクセル x 96 ピクセル、Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、Microsoft Lync Web App、Lync 2013 を使用できます。

  - 648ピクセル、648ピクセル、Lync 2013 および Microsoft Lync Web App で使用できます。

<div>


> [!NOTE]  
> リソースを確保できる場合は、648 × 648 の写真をアップロードすることをお勧めします。これにより、Office 2013 のどのアプリケーションにおいても最大の解像度と最適な写真の画質を実現できます。サイズが 648 × 648、ビットの深さが 24 の JPEG の写真の場合、ファイル サイズは約 240 KB になります。つまり、ユーザーの写真 4 枚ごとに約 1 MB のディスク容量が必要です。



</div>

Exchange Web Services を使用してアクセスできる高解像度写真は、Outlook 2013 Web App を実行しているユーザーがアップロードできます。ユーザーは自分の写真を更新することのみ許可されています。 ただし、管理者は、Exchange 管理シェルと、次のような一連の Windows PowerShell コマンドを使用して、任意のユーザーの写真を更新することができます。

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

上の例の最初のコマンドでは、コンテンツの取得コマンドレットを使用してファイル C:\\Photos\\の内容を読み取り、そのデータを $photo という名前の変数に格納しています。 2番目のコマンドでは、Exchange コマンドレットが設定された UserPhoto を使って写真をアップロードし、その写真を Ken Myer のユーザーアカウントに添付します。

<div>


> [!NOTE]  
> この例では、Ken Myer の Active Directory 表示名がユーザー アカウントの ID として使用されています。 また、その他の識別子 (ユーザーの SMTP アドレスやユーザー プリンシパル名など) を使用してユーザー アカウントを参照することもできます。 詳細<A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A>については、「Set-userphoto コマンドレットのドキュメント」を参照してください。



</div>

写真のアップロードは、その写真を Ken Myer のユーザー アカウントに割り当てる操作と同じではありません。写真のアップロードは、Outlook Web App の [オプション] ページに表示されるその写真のプレビューにすぎません。写真を実際にユーザー アカウントに割り当てるには、[オプション] ページの [**保存**] をクリックするか、例に示す 3 つ目のコマンドを管理者が実行する必要があります。3 つ目のコマンドでは、Save パラメーターを使用して写真を Ken Myer のユーザー アカウントに割り当てます。

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

新しい写真がユーザーアカウントに割り当てられていることを確認するために、Ken Myer は Lync 2013 にログオンして、[**オプション**] を選び、[**マイピクチャ**] を選ぶことができます。 新しくアップロードされた写真が Ken の個人用の写真として表示されるはずです。 また、管理者が Internet Explorer を起動し、次のような URL にアクセスしてユーザーの写真を確認することもできます。

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

管理者が Internet Explorer を使って写真を表示できるが、ユーザーが Lync 2013 で自分の写真を表示できない場合、通常は Exchange Web Services または Exchange 自動検出サービスとの接続に問題があることを示します。

この写真を Lync 2013 で利用できるようにするために、追加の構成は必要ないことに注意してください。 写真がアップロードされて Set-UserPhoto コマンドレットを実行すると、即時に利用できるようになります。

</div>

<span> </span>

</div>

</div>

</div>

