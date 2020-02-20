---
title: 'Lync Server 2013: 高解像度写真の使用の構成'
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
ms.openlocfilehash: ec832d3795fc1b83c6a838b15c04be9f2e48d6d0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a>Microsoft Lync Server 2013 で高解像度写真の使用を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-05_

Microsoft Lync Server 2010 は、ユーザーが連絡先の写真を表示する機能を提供しました (また、他のユーザーが自分の写真を使用できるようにするため)。 通常、これらの写真は、Active Directory のユーザーの thumbnailPhoto 属性の一部として保存されていました。 写真のサイズと解像度に関して深刻な制限が適用されました。 thumbnailPhoto 属性には、最大サイズが48ピクセル、48ピクセルの写真のみを保持できます。

ただし、Microsoft Lync Server 2013 では、ユーザーの Microsoft Exchange Server 2013 メールボックスに写真を格納することができます。これにより、写真のサイズを最大648ピクセル、648ピクセルにすることができます。 これに加えて、Exchange 2013 は、必要に応じて異なる製品で使用するためにこれらの写真のサイズを自動的に変更することができます。 通常、3つの異なる写真のサイズと解像度を意味します。

  - 48ピクセル x 48 ピクセル、Active Directory thumbnailPhoto 属性で使用されるサイズ。 Exchange 2013 に写真をアップロードすると、Exchange はその写真の 48 48 ピクセルバージョンを自動的に作成し、ユーザーの thumbnailPhoto 属性を更新します。 ただし、その逆は true ではないことに注意してください。 Active Directory で thumbnailPhoto 属性を手動で更新した場合、ユーザーの Exchange 2013 メールボックス内の写真は自動的に更新されません。

  - 96ピクセル、96ピクセル、Microsoft Outlook 2013 Web App、microsoft Outlook 2013、microsoft Lync Web App、および Lync 2013 で使用します。

  - 648ピクセル x 648 ピクセル、Lync 2013 および Microsoft Lync Web App で使用します。

<div>


> [!NOTE]  
> リソースを確保できる場合は、648 × 648 の写真をアップロードすることをお勧めします。これにより、Office 2013 のどのアプリケーションにおいても最大の解像度と最適な写真の画質を実現できます。サイズが 648 × 648、ビットの深さが 24 の JPEG の写真の場合、ファイル サイズは約 240 KB になります。つまり、ユーザーの写真 4 枚ごとに約 1 MB のディスク容量が必要です。



</div>

Exchange Web サービスを使用してアクセスされる高解像度写真は、Outlook 2013 Web App を実行しているユーザーがアップロードできます。ユーザーは自分の写真を更新することしか許可されていません。 ただし、管理者は、Exchange 管理シェルと、次のような一連の Windows PowerShell コマンドを使用して、任意のユーザーの写真を更新できます。

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

前の例の最初のコマンドでは、取得したコマンドレットを使用してファイル C:\\Photos\\の内容を読み取り、そのデータを $photo という名前の変数に格納します。 2番目のコマンドでは、Exchange コマンドレットの設定-UserPhoto を使用して写真をアップロードし、その写真を Ken Myer のユーザーアカウントに添付します。

<div>


> [!NOTE]  
> この例では、Ken Myer の Active Directory 表示名がユーザー アカウントの ID として使用されています。 また、その他の識別子 (ユーザーの SMTP アドレスやユーザー プリンシパル名など) を使用してユーザー アカウントを参照することもできます。 詳細<A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A>については、このコマンドレットのドキュメントを参照してください。



</div>

写真のアップロードは、その写真を Ken Myer のユーザー アカウントに割り当てる操作と同じではありません。写真のアップロードは、Outlook Web App の [オプション] ページに表示されるその写真のプレビューにすぎません。写真を実際にユーザー アカウントに割り当てるには、[オプション] ページの [**保存**] をクリックするか、例に示す 3 つ目のコマンドを管理者が実行する必要があります。3 つ目のコマンドでは、Save パラメーターを使用して写真を Ken Myer のユーザー アカウントに割り当てます。

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

新しい写真がユーザーアカウントに割り当てられていることを確認するには、Ken Myer が Lync 2013 にログオンし、[**オプション**] を選択して、[**マイピクチャ**] を選択します。 新しくアップロードされた写真が Ken の個人用の写真として表示されるはずです。 また、管理者が Internet Explorer を起動し、次のような URL にアクセスしてユーザーの写真を確認することもできます。

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

管理者が Internet Explorer を使用して写真を表示でき、ユーザーが Lync 2013 で写真を表示できない場合は、通常、Exchange Web サービスまたは Exchange 自動検出サービスとの接続の問題が発生しています。

また、Lync 2013 でこの写真を利用できるようにするために、追加の構成は不要です。 その代わりに、アップロードされた写真がすぐに使用可能になり、ユーザーの設定-UserPhoto コマンドレットが実行されます。

</div>

<span> </span>

</div>

</div>

</div>

