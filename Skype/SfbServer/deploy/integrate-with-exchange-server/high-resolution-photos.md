---
title: Skype for Business Server で高解像度写真の使用を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: '概要: Exchange Server 2019、Exchange Server 2016、Exchange Server 2013、Exchange Online および Skype for Business Server で高解像度写真の使用を構成します。'
ms.openlocfilehash: c55e5a90e222ea024dd63f72b26627141b2f113e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834007"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a><span data-ttu-id="f7a78-103">Skype for Business Server で高解像度写真の使用を構成する</span><span class="sxs-lookup"><span data-stu-id="f7a78-103">Configure the use of high-resolution photos in Skype for Business Server</span></span>
 
<span data-ttu-id="f7a78-104">**概要:** Exchange Server 2019、Exchange Server 2016、Exchange Server 2013、または Exchange Online と Skype for Business Server で高解像度写真の使用を構成します。</span><span class="sxs-lookup"><span data-stu-id="f7a78-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online and Skype for Business Server.</span></span>
  
<span data-ttu-id="f7a78-105">Skype for Business Server では、写真をユーザーの Exchange Server 2019、Exchange Server 2016、Exchange Server 2013、または Exchange Online メールボックスに格納できます。これにより、最大 648 ピクセル × 648 ピクセルの写真サイズが可能になります。</span><span class="sxs-lookup"><span data-stu-id="f7a78-105">In Skype for Business Server, photos can be stored in a user's Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="f7a78-106">さらに、これらのExchange Server、必要に応じてさまざまな製品で使用するために、これらの写真のサイズを自動的に変更できます。</span><span class="sxs-lookup"><span data-stu-id="f7a78-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="f7a78-107">通常、次の 3 つの異なる写真のサイズと解像度を意味します。</span><span class="sxs-lookup"><span data-stu-id="f7a78-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="f7a78-108">64 × 64 ピクセル、Active Directory thumbnailPhoto 属性に使用されるサイズ。</span><span class="sxs-lookup"><span data-stu-id="f7a78-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="f7a78-109">Exchange Server に写真をアップロードすると、Exchange によってその写真の 64 ピクセル バージョンが自動的に作成され、ユーザーの thumbnailPhoto 属性が更新されます。</span><span class="sxs-lookup"><span data-stu-id="f7a78-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="f7a78-110">ただし、逆の点に注意してください。Active Directory の thumbnailPhoto 属性を手動で更新すると、ユーザーの Exchange メールボックス内の写真は自動的に更新されません。</span><span class="sxs-lookup"><span data-stu-id="f7a78-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="f7a78-111">Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、Skype for Business Web App、Skype for Business で使用する場合は、96 × 96 ピクセル。</span><span class="sxs-lookup"><span data-stu-id="f7a78-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="f7a78-112">Skype for Business および Skype for Business Web App Skype for Business Web App で使用する 648 × 648 ピクセル。</span><span class="sxs-lookup"><span data-stu-id="f7a78-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f7a78-113">リソースがある場合は、648 x 648 の写真をアップロードしてください。を使用して、任意のアプリケーションで最大解像度と最適な画像Office 2013します。</span><span class="sxs-lookup"><span data-stu-id="f7a78-113">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="f7a78-114">サイズが 648 x 648 で、深度が 24 ビットの JPEG の各写真のファイル サイズは約 240 キロバイトになります。</span><span class="sxs-lookup"><span data-stu-id="f7a78-114">Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="f7a78-115">つまり、ユーザーの写真 4 枚ごとに約 1 MB のディスク領域が必要になります。</span><span class="sxs-lookup"><span data-stu-id="f7a78-115">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="f7a78-116">Exchange Web サービスを使用してアクセスされる高解像度の写真は、Outlook 2013 Web App を実行しているユーザーがアップロードできます。ユーザーは自分の写真の更新のみを許可されます。</span><span class="sxs-lookup"><span data-stu-id="f7a78-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="f7a78-117">ただし、管理者は、Exchange 管理シェル と次のような一連の Windows PowerShell コマンドを使用して、すべてのユーザーの写真を更新できます。</span><span class="sxs-lookup"><span data-stu-id="f7a78-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="f7a78-118">前の例の最初のコマンドでは、コマンドレットを使用してファイル ファイルの内容を読み取りC:\Photos\Kenmyer.jpg、そのデータを $photo という名前の変数に `Get-Content` 格納します。</span><span class="sxs-lookup"><span data-stu-id="f7a78-118">The first command in the preceding example uses the `Get-Content` cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="f7a78-119">2 番目のコマンドでは、Exchange コマンドレットを使用して写真をアップロードし、その写真を Ken Myer のユーザー アカウント `Set-UserPhoto` に添付します。</span><span class="sxs-lookup"><span data-stu-id="f7a78-119">In the second command, the Exchange cmdlet `Set-UserPhoto` is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f7a78-120">この例では、Ken Myer の Active Directory 表示名がユーザー アカウントの ID として使用されています。</span><span class="sxs-lookup"><span data-stu-id="f7a78-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="f7a78-121">また、その他の識別子 (ユーザーの SMTP アドレスやユーザー プリンシパル名など) を使用してユーザー アカウントを参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="f7a78-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="f7a78-122">詳細については、Set-UserPhoto コマンドレットのドキュメント [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7a78-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) for more information</span></span>
  
<span data-ttu-id="f7a78-p107">写真のアップロードは、その写真を Ken Myer のユーザー アカウントに割り当てる操作と同じではありません。写真のアップロードは、Outlook Web App の [オプション] ページに表示されるその写真のプレビューにすぎません。写真を実際にユーザー アカウントに割り当てるには、[オプション] ページの [**保存**] をクリックするか、例に示す 3 つ目のコマンドを管理者が実行する必要があります。3 つ目のコマンドでは、Save パラメーターを使用して写真を Ken Myer のユーザー アカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f7a78-p107">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="f7a78-127">新しい写真がユーザー アカウントに割り当てられているを確認するために、Ken Myer は Skype for Business にログオンし、[オプション] を選択して、[マイ ピクチャ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f7a78-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="f7a78-128">新しくアップロードされた写真が Ken の個人用の写真として表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="f7a78-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="f7a78-129">また、管理者が Internet Explorer を起動し、次のような URL にアクセスしてユーザーの写真を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="f7a78-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

<span data-ttu-id="f7a78-130">管理者が Internet Explorer を使用して写真を表示できるが、ユーザーが Skype for Business で自分の写真を表示できない場合は、Exchange Web サービスまたは Exchange 自動検出サービスとの接続に問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f7a78-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="f7a78-131">また、この写真を Skype for Business で利用するために追加の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f7a78-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="f7a78-132">代わりに、写真はアップロードされ、コマンドレットが実行された後すぐに `Set-UserPhoto` 利用できます。</span><span class="sxs-lookup"><span data-stu-id="f7a78-132">Instead, the photo will be instantly available after it has been uploaded and the `Set-UserPhoto` cmdlet has been run.</span></span>
