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
ms.openlocfilehash: e817e86d6f05291192593e2345b9e4bc1c0b6db3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517360"
---
# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a><span data-ttu-id="e8574-102">Microsoft Lync Server 2013 で高解像度写真の使用を構成する</span><span class="sxs-lookup"><span data-stu-id="e8574-102">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8574-103">_**トピックの最終更新日:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="e8574-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="e8574-104">Microsoft Lync Server 2010 は、ユーザーが連絡先の写真を表示する機能を提供しました (また、他のユーザーが自分の写真を使用できるようにするため)。</span><span class="sxs-lookup"><span data-stu-id="e8574-104">Microsoft Lync Server 2010 provided the ability for users to view photos of their contacts (and to make their own photos available to others).</span></span> <span data-ttu-id="e8574-105">通常、これらの写真は、Active Directory のユーザーの thumbnailPhoto 属性の一部として保存されていました。</span><span class="sxs-lookup"><span data-stu-id="e8574-105">Typically these photos were stored as part of the user's thumbnailPhoto attribute in Active Directory.</span></span> <span data-ttu-id="e8574-106">写真のサイズと解像度に関して深刻な制限が適用されました。 thumbnailPhoto 属性には、最大サイズが48ピクセル、48ピクセルの写真のみを保持できます。</span><span class="sxs-lookup"><span data-stu-id="e8574-106">That placed a serious limitation on the size and resolution of the photos: the thumbnailPhoto attribute can only hold a photograph with a maximum size of 48 pixels by 48 pixels.</span></span>

<span data-ttu-id="e8574-107">ただし、Microsoft Lync Server 2013 では、ユーザーの Microsoft Exchange Server 2013 メールボックスに写真を格納することができます。これにより、写真のサイズを最大648ピクセル、648ピクセルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e8574-107">In Microsoft Lync Server 2013, however, photos can be stored in a user's Microsoft Exchange Server 2013 mailbox; that allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="e8574-108">これに加えて、Exchange 2013 は、必要に応じて異なる製品で使用するためにこれらの写真のサイズを自動的に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e8574-108">In addition to that, Exchange 2013 can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="e8574-109">通常、3つの異なる写真のサイズと解像度を意味します。</span><span class="sxs-lookup"><span data-stu-id="e8574-109">Typically that means three different photo sizes and resolutions:</span></span>

  - <span data-ttu-id="e8574-110">48ピクセル x 48 ピクセル、Active Directory thumbnailPhoto 属性で使用されるサイズ。</span><span class="sxs-lookup"><span data-stu-id="e8574-110">48 pixels by 48 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="e8574-111">Exchange 2013 に写真をアップロードすると、Exchange はその写真の 48 48 ピクセルバージョンを自動的に作成し、ユーザーの thumbnailPhoto 属性を更新します。</span><span class="sxs-lookup"><span data-stu-id="e8574-111">If you upload a photo to Exchange 2013 Exchange will automatically create a 48 pixel by 48 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="e8574-112">ただし、その逆は true ではないことに注意してください。 Active Directory で thumbnailPhoto 属性を手動で更新した場合、ユーザーの Exchange 2013 メールボックス内の写真は自動的に更新されません。</span><span class="sxs-lookup"><span data-stu-id="e8574-112">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange 2013 mailbox will not automatically be updated.</span></span>

  - <span data-ttu-id="e8574-113">96ピクセル、96ピクセル、Microsoft Outlook 2013 Web App、microsoft Outlook 2013、microsoft Lync Web App、および Lync 2013 で使用します。</span><span class="sxs-lookup"><span data-stu-id="e8574-113">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App, and Lync 2013.</span></span>

  - <span data-ttu-id="e8574-114">648ピクセル x 648 ピクセル、Lync 2013 および Microsoft Lync Web App で使用します。</span><span class="sxs-lookup"><span data-stu-id="e8574-114">648 pixels by 648 pixels for use in Lync 2013 and Microsoft Lync Web App.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8574-p104">リソースを確保できる場合は、648 × 648 の写真をアップロードすることをお勧めします。これにより、Office 2013 のどのアプリケーションにおいても最大の解像度と最適な写真の画質を実現できます。サイズが 648 × 648、ビットの深さが 24 の JPEG の写真の場合、ファイル サイズは約 240 KB になります。つまり、ユーザーの写真 4 枚ごとに約 1 MB のディスク容量が必要です。</span><span class="sxs-lookup"><span data-stu-id="e8574-p104">If you have the resources, it is recommended that you upload 648x648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications. Each JPEG photo with a size of 648x648 and a depth of 24 bits results in a file size of approximately 240 kilobytes. That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span>



</div>

<span data-ttu-id="e8574-118">Exchange Web サービスを使用してアクセスされる高解像度写真は、Outlook 2013 Web App を実行しているユーザーがアップロードできます。ユーザーは自分の写真を更新することしか許可されていません。</span><span class="sxs-lookup"><span data-stu-id="e8574-118">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="e8574-119">ただし、管理者は、Exchange 管理シェルと、次のような一連の Windows PowerShell コマンドを使用して、任意のユーザーの写真を更新できます。</span><span class="sxs-lookup"><span data-stu-id="e8574-119">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="e8574-120">前の例の最初のコマンドでは Get-Content コマンドレットを使用して、ファイル C: PhotosKenmyer.jpg の内容を読み取り、 \\ \\ そのデータを $photo という名前の変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="e8574-120">The first command in the preceding example uses the Get-Content cmdlet to read the contents of the file C:\\Photos\\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="e8574-121">2番目のコマンドでは、Exchange コマンドレット Set-UserPhoto を使用して写真をアップロードし、その写真を Ken Myer のユーザーアカウントに添付します。</span><span class="sxs-lookup"><span data-stu-id="e8574-121">In the second command, the Exchange cmdlet Set-UserPhoto is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8574-122">この例では、Ken Myer の Active Directory 表示名がユーザー アカウントの ID として使用されています。</span><span class="sxs-lookup"><span data-stu-id="e8574-122">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="e8574-123">また、その他の識別子 (ユーザーの SMTP アドレスやユーザー プリンシパル名など) を使用してユーザー アカウントを参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="e8574-123">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="e8574-124">詳細については、Set-UserPhoto コマンドレットのドキュメントを参照してください。 <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A></span><span class="sxs-lookup"><span data-stu-id="e8574-124">See the documentation for the Set-UserPhoto cmdlet at <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A> for more information</span></span>



</div>

<span data-ttu-id="e8574-p108">写真のアップロードは、その写真を Ken Myer のユーザー アカウントに割り当てる操作と同じではありません。写真のアップロードは、Outlook Web App の [オプション] ページに表示されるその写真のプレビューにすぎません。写真を実際にユーザー アカウントに割り当てるには、[オプション] ページの [**保存**] をクリックするか、例に示す 3 つ目のコマンドを管理者が実行する必要があります。3 つ目のコマンドでは、Save パラメーターを使用して写真を Ken Myer のユーザー アカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e8574-p108">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="e8574-129">新しい写真がユーザーアカウントに割り当てられていることを確認するには、Ken Myer が Lync 2013 にログオンし、[ **オプション**] を選択して、[ **マイピクチャ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8574-129">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Lync 2013, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="e8574-130">新しくアップロードされた写真が Ken の個人用の写真として表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="e8574-130">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="e8574-131">また、管理者が Internet Explorer を起動し、次のような URL にアクセスしてユーザーの写真を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="e8574-131">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

<span data-ttu-id="e8574-132">管理者が Internet Explorer を使用して写真を表示でき、ユーザーが Lync 2013 で写真を表示できない場合は、通常、Exchange Web サービスまたは Exchange 自動検出サービスとの接続の問題が発生しています。</span><span class="sxs-lookup"><span data-stu-id="e8574-132">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Lync 2013, that typically indicates a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>

<span data-ttu-id="e8574-133">また、Lync 2013 でこの写真を利用できるようにするために、追加の構成は不要です。</span><span class="sxs-lookup"><span data-stu-id="e8574-133">Note, too that no additional configuration is required in order to make this photo available in Lync 2013.</span></span> <span data-ttu-id="e8574-134">その代わりに、アップロードされた写真はすぐに使用可能になり、Set-UserPhoto コマンドレットが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e8574-134">Instead, the photo will be instantly available after it has been uploaded and the Set-UserPhoto cmdlet has been run.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

