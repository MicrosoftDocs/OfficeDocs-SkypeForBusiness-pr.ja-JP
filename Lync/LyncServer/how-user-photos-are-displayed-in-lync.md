---
title: Lync でユーザーの写真を表示する方法
description: ユーザーの写真が Lync でどのように表示されるか。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12ea9e19b3965994c025659f1b2249c49ec32a3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551113"
---
# <a name="how-user-photos-are-displayed-in-lync"></a><span data-ttu-id="c7c31-103">Lync でユーザーの写真を表示する方法</span><span class="sxs-lookup"><span data-stu-id="c7c31-103">How user photos are displayed in Lync</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7c31-104">_**トピックの最終更新日:** 2014-08-25_</span><span class="sxs-lookup"><span data-stu-id="c7c31-104">_**Topic Last Modified:** 2014-08-25_</span></span>

<span data-ttu-id="c7c31-105">**概要:** Lync クライアントに表示されるユーザーの写真は、会議や IM チャットなど、どの Lync 機能を使用しているかによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c7c31-105">**Summary:** User photos displayed in Lync client can be different depending on which Lync feature you are using, such as when in a conference or an IM chat.</span></span>

<span data-ttu-id="c7c31-106">Lync 2010 には、他の Lync ユーザーに表示される Lync プロファイルに写真を含める機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="c7c31-106">Lync 2010 introduced the ability to include a photo with your Lync profile that is displayed to other Lync users.</span></span> <span data-ttu-id="c7c31-107">また、Lync クライアントで連絡先の写真を表示するかどうかを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-107">You can also choose whether or not to display photos for your contacts in Lync client.</span></span> <span data-ttu-id="c7c31-108">Lync 2013 では、ユーザーの高解像度写真のサポートがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c7c31-108">In Lync 2013, support for high-resolution photos for users.</span></span> <span data-ttu-id="c7c31-109">このトピックでは、Lync クライアントがユーザーの写真を取得および表示する方法、画像が格納される場所、各画像ソースの制限、およびさまざまな Lync サービスでユーザーの写真を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7c31-109">This topic describes how Lync client gets and displays user photos, where the images are stored, the limitations for each image source, and how user photos are used by different Lync services.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="c7c31-110">計画に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="c7c31-110">Planning considerations</span></span>

<span data-ttu-id="c7c31-111">ユーザー写真のサポートの実装を計画するときは、次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7c31-111">You should consider the following when planning to implement support for user photos.</span></span>

  - <span data-ttu-id="c7c31-112">高精細ユーザーの写真サポートを使用するには、ユーザーのメールボックスが Exchange 2013 上にあり、lync ユーザーアカウントが Lync 2013 プールに配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7c31-112">High-definition user photo support requires that the user’s mailbox be located on Exchange 2013 and the Lync user account to be in Lync 2013 pool.</span></span>

  - <span data-ttu-id="c7c31-113">高精細ユーザーの写真は、Lync Server 2013 と Exchange 2013 の両方が使用されている環境でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-113">High-definition user photos are supported only in an environment where both Lync Server 2013 and Exchange 2013 are used.</span></span>

  - <span data-ttu-id="c7c31-114">Exchange 2010 上にメールボックスを持つユーザーは、常に、ユーザー写真のソースとして AD DS の **thumbnailPhoto** 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="c7c31-114">Users with Mailboxes on Exchange 2010 will always use the **thumbnailPhoto** attribute from AD DS as the source for their user photo.</span></span>

  - <span data-ttu-id="c7c31-115">AD DS から **thumbnailPhoto** 属性として保存されたユーザー写真は、外部/フェデレーションの連絡先に表示されません。</span><span class="sxs-lookup"><span data-stu-id="c7c31-115">A user photo stored as the **thumbnailPhoto** attribute from AD DS will not be displayed to external / federated contacts.</span></span>

  - <span data-ttu-id="c7c31-116">ユーザーの連絡先の写真が AD DS に保存されている場合、使用される画像ファイルは96×96ピクセルに制限され、100 KB のファイルサイズを超えないようにします。</span><span class="sxs-lookup"><span data-stu-id="c7c31-116">If the photos for user contacts are stored in AD DS, the image file used is limited to 96×96 pixels and no more than 100 KB file size.</span></span>

  - <span data-ttu-id="c7c31-117">Lync Server と Exchange Server の間の接続が失われた場合、AD DS からのユーザーの低解像度 **thumbnailPhoto** が表示され、内部ユーザーのみになります。</span><span class="sxs-lookup"><span data-stu-id="c7c31-117">If connectivity between Lync Server and Exchange Server is lost, the user’s low resolution **thumbnailPhoto** from AD DS will be displayed, and to internal users only.</span></span>

  - <span data-ttu-id="c7c31-118">アクティブなスピーカーでビデオが有効になっていない場合、高解像度のユーザー写真が Lync 2013 会議に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-118">High-resolution user photos are displayed in Lync 2013 meetings when an active speaker does not have video enabled.</span></span> <span data-ttu-id="c7c31-119">また、ギャラリーのサムネイル写真の上にマウスポインターを移動すると、高解像度写真が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-119">Also, moving the mouse over thumbnail photo in the gallery will display the high-resolution photo.</span></span>

</div>

<div>

## <a name="user-photos-in-lync-2010"></a><span data-ttu-id="c7c31-120">Lync 2010 のユーザーの写真</span><span class="sxs-lookup"><span data-stu-id="c7c31-120">User Photos in Lync 2010</span></span>

<span data-ttu-id="c7c31-121">Lync 2010 クライアントでは、次の2つのオプションのいずれかを選択して、プロファイルの写真を表示したり、 **既定の企業画像** を表示したり、 **web アドレスから画像を表示**したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-121">In the Lync 2010 client, you can choose from two options to display a photo for your profile, **Default corporate picture** and **Show picture from a web address**.</span></span>

<div>

## <a name="default-corporate-picture"></a><span data-ttu-id="c7c31-122">既定のコーポレート ピクチャ</span><span class="sxs-lookup"><span data-stu-id="c7c31-122">Default corporate picture</span></span>

<span data-ttu-id="c7c31-123">[ **既定の会社画像** ] オプションを選択すると、Lync は Active Directory ドメインサービスから表示される写真を取得します。</span><span class="sxs-lookup"><span data-stu-id="c7c31-123">When you choose the **Default corporate picture** option, Lync gets the photo displayed for you from Active Directory Domain Services.</span></span> <span data-ttu-id="c7c31-124">使用されるイメージは、Active Directory ドメインサービスの **thumbnailPhoto** 属性の値として定義されたイメージです。</span><span class="sxs-lookup"><span data-stu-id="c7c31-124">The image used is the image defined as the value for the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span> <span data-ttu-id="c7c31-125">これは、Exchange が Outlook で画像を表示するときに使用するファイルと同じです。</span><span class="sxs-lookup"><span data-stu-id="c7c31-125">This is the same file that is used by Exchange to display images in Outlook.</span></span>

<span data-ttu-id="c7c31-126">Active Directory ドメインサービスからイメージを使用する場合の考慮事項は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c7c31-126">Considerations for using images from Active Directory Domain Services include the following:</span></span>

  - <span data-ttu-id="c7c31-127">最大96ピクセル、96ピクセルの大きさの画像のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-127">Only images with dimensions up to 96 pixels by 96 pixels are supported.</span></span> <span data-ttu-id="c7c31-128">画像のファイルサイズは 100 KB に制限されています。</span><span class="sxs-lookup"><span data-stu-id="c7c31-128">The file size for the image is limited to 100 KB.</span></span>

  - <span data-ttu-id="c7c31-129">既定では、ユーザーは **thumbnailPhoto** 属性に使用されているイメージを変更できます。ただし、Lync クライアントを直接使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c7c31-129">By default, users are able to change the image used for the **thumbnailPhoto** attribute, though not directly through Lync client.</span></span> <span data-ttu-id="c7c31-130">Active Directory ドメインサービスを使用してこれを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-130">You can disable this through Active Directory Domain Services.</span></span>

  - <span data-ttu-id="c7c31-131">Active Directory ドメインサービスに保存された画像は、フェデレーションされた連絡先であっても、組織外の連絡先には表示されません。</span><span class="sxs-lookup"><span data-stu-id="c7c31-131">Images stored in Active Directory Domain Services are not displayed to contacts external to your organization, even if they are federated contacts.</span></span>

  - <span data-ttu-id="c7c31-132">大規模な組織では、大量のユーザー用の画像を格納して取得することは、Active Directory ドメインサービスデータベースのサイズとパフォーマンスに影響することがあります。</span><span class="sxs-lookup"><span data-stu-id="c7c31-132">In large organizations, storing and retrieving the images for large numbers of users may impact the Active Directory Domain Services database size and performance.</span></span>

  - <span data-ttu-id="c7c31-133">画像のサイズが制限され、ファイルのサイズが小さいため、低解像度の画像しか使用できません。</span><span class="sxs-lookup"><span data-stu-id="c7c31-133">The limited image dimensions and file size mean that only low resolution images can be used.</span></span>

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a><span data-ttu-id="c7c31-134">ユーザーが Active Directory ドメインサービスでユーザーの写真を管理する方法</span><span class="sxs-lookup"><span data-stu-id="c7c31-134">How users manage their user photos in Active Directory Domain Services</span></span>

<span data-ttu-id="c7c31-135">ユーザーは、Lync 2010 クライアントを使用して、Active Directory ドメインサービスプロファイルで使用されているイメージを直接変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c7c31-135">User cannot change the image used in their Active Directory Domain Services profile directly through Lync 2010 client.</span></span> <span data-ttu-id="c7c31-136">そのためには、次のいずれかのオプションを使用できます (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="c7c31-136">They can use one of the following options to do so, if available:</span></span>

  - <span data-ttu-id="c7c31-137">**SharePoint Server**    ユーザーは、SharePoint サーバー上の [個人用サイト] に写真をアップロードし、 [sharepoint でプロファイルの同期を構成](https://go.microsoft.com/fwlink/p/?linkid=507466)して、Active Directory ドメインサービスの**thumbnailPhoto**属性に写真を同期させることができます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-137">**SharePoint Server**   Users can upload a photo to ‘My Site’ on a SharePoint Server and then [configure profile synchronization in SharePoint](https://go.microsoft.com/fwlink/p/?linkid=507466) to synchronize the photo to the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="c7c31-138">**パブリックにアクセス可能な URL**     に保存された写真ユーザーは、使用するイメージに対して、公開されているアクセス可能な URL を指定してユーザーの写真を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-138">**Photo stored on publicly accessible URL**   Users can configure their user photo specifying a publicly accessible URL for the image that they want to use.</span></span> <span data-ttu-id="c7c31-139">画像は、パスワードを使用せずに、一般にアクセス可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7c31-139">The image must be publicly accessible without a password.</span></span> <span data-ttu-id="c7c31-140">指定した web アドレスに格納されているイメージは、プレゼンス情報の連絡先カードカテゴリを通じて他のユーザーに転送されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-140">The image stored at the specified web address is transferred to other users through the contact card category in the presence information.</span></span> <span data-ttu-id="c7c31-141">Lync クライアントがユーザーの写真を表示する必要がある場合は、指定された web アドレスから画像を取得します。</span><span class="sxs-lookup"><span data-stu-id="c7c31-141">When Lync client needs to display a user photo, it retrieves the image from the specified web address.</span></span>

  - <span data-ttu-id="c7c31-142">**Windows PowerShell**     の Exchange 2010 コマンドレット管理者は、 **thumbnailPhoto**属性を管理するために、の Exchange 2010 管理シェルで、[インポート-受信者データプロパティ](https://go.microsoft.com/fwlink/p/?linkid=507468)コマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-142">**Exchange 2010 cmdlets for Windows PowerShell**   Administrators can run the [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet in the Exchange 2010 Management Shell in to manage the **thumbnailPhoto** attribute.</span></span> <span data-ttu-id="c7c31-143">Exchange 2010 コマンドレットを使用して画像をインポートする場合、ファイルのサイズは 10 KB に制限されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-143">When images are imported with Exchange 2010 cmdlets, the file size is limited to 10 KB.</span></span>

  - <span data-ttu-id="c7c31-144">**サードパーティ製のツール**    ユーザーは自分の写真のみを**thumbnailPhoto**属性にアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-144">**Third Party tools**   Users can upload only their own photo to for the **thumbnailPhoto** attribute.</span></span>

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a><span data-ttu-id="c7c31-145">Web アドレスからピクチャを表示する</span><span class="sxs-lookup"><span data-stu-id="c7c31-145">Show a picture from a web address</span></span>

<span data-ttu-id="c7c31-146">[ **Web アドレスから画像を表示** する] オプションを選択すると、入力したアドレスで画像が取得され、lync でユーザーの写真が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-146">When you choose the **Show a picture from a web address** option, Lync gets the image at the address you enter and displays it for your user photo in Lync.</span></span>

<span data-ttu-id="c7c31-147">Web アドレスから画像を使用する場合の考慮事項は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c7c31-147">Considerations for using images from a web address include the following:</span></span>

  - <span data-ttu-id="c7c31-148">ファイルサイズの制限は、[新しい-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463)コマンドレットで定義された、クライアントポリシーの**Maxphotosizekb**属性によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-148">File size limits are determined by the **MaxPhotoSizeKB** attribute in the client policy, defined with the [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet.</span></span> <span data-ttu-id="c7c31-149">既定のサイズ制限は 30 KB です。</span><span class="sxs-lookup"><span data-stu-id="c7c31-149">The default size limit is 30 KB.</span></span> <span data-ttu-id="c7c31-150">最大値は 100 KB です。</span><span class="sxs-lookup"><span data-stu-id="c7c31-150">The maximum value is 100 KB.</span></span> <span data-ttu-id="c7c31-151">画像の解像度に制限はありませんが、サイズ制限を超える画像ファイルを使用しようとすると、Lync クライアントにダウンロードされません。</span><span class="sxs-lookup"><span data-stu-id="c7c31-151">There is no restriction on the resolution of the image, but if you try to use an image file that exceeds the size limit it will not be downloaded to Lync clients.</span></span> <span data-ttu-id="c7c31-152">この値を0に設定すると、Lync でのすべてのユーザーの写真の使用を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-152">You can set the value to 0 to disable all user photos from being used in Lync.</span></span>

  - <span data-ttu-id="c7c31-153">Web アドレスからのユーザーの写真は、外部フェデレーションの連絡先に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-153">User photos from a web address can be seen by external federated contacts.</span></span>

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a><span data-ttu-id="c7c31-154">クライアントポリシーコマンドレットを使用してユーザーの写真を管理する</span><span class="sxs-lookup"><span data-stu-id="c7c31-154">Managing user’s photo with Client Policy cmdlets</span></span>

<span data-ttu-id="c7c31-155">Lync Server 2010 では、クライアントポリシー設定が CsClientPolicy コマンドレットを使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-155">In Lync Server 2010, client policy settings are configured with the CsClientPolicy cmdlets.</span></span> <span data-ttu-id="c7c31-156">構成済みのポリシー設定は、インバンドプロビジョニングを通じてクライアントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-156">The configured policy settings are sent to clients through in-band provisioning.</span></span> <span data-ttu-id="c7c31-157">ユーザーの写真の表示を決定する CsClientPolicy コマンドレットの2つのパラメーターは、 **DisplayPhoto** と **Maxphotosizekb**です。</span><span class="sxs-lookup"><span data-stu-id="c7c31-157">The two parameters of the CsClientPolicy cmdlets that determine the user photo experience are **DisplayPhoto** and **MaxPhotoSizeKB**.</span></span> <span data-ttu-id="c7c31-158">**DisplayPhoto**の対応するインバンドプロビジョニングパラメーターと**Maxphotosizekb**は、 **PhotoUsage**という名前です。</span><span class="sxs-lookup"><span data-stu-id="c7c31-158">The corresponding in-band provisioning parameter for **DisplayPhoto** and **MaxPhotoSizeKB** is named **PhotoUsage**.</span></span> <span data-ttu-id="c7c31-159">**PhotoUsage**パラメーターの値は、 **endpointConfiguration** **provisionGroup**を使用してクライアントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-159">Values for the **PhotoUsage** parameter are send to clients through the **endpointConfiguration** **provisionGroup**.</span></span> <span data-ttu-id="c7c31-160">詳細については [、「クライアントポリシーと設定の概要](https://go.microsoft.com/fwlink/?linkid=507470) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7c31-160">See [Overview of Client Policies and Settings](https://go.microsoft.com/fwlink/?linkid=507470) for more information.</span></span>

<span data-ttu-id="c7c31-161">**DisplayPhoto**パラメーターの値は、ユーザーの写真の画像のソースを決定します。</span><span class="sxs-lookup"><span data-stu-id="c7c31-161">The **DisplayPhoto** parameter value determines the source of the user's photo image.</span></span> <span data-ttu-id="c7c31-162">次の表に、サポートされている値を示します。</span><span class="sxs-lookup"><span data-stu-id="c7c31-162">The supported values are included in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7c31-163">DisplayPhoto パラメーターの値</span><span class="sxs-lookup"><span data-stu-id="c7c31-163">DisplayPhoto parameter value</span></span></th>
<th><span data-ttu-id="c7c31-164">画像ソース</span><span class="sxs-lookup"><span data-stu-id="c7c31-164">Image source</span></span></th>
<th><span data-ttu-id="c7c31-165">Lync 2010 クライアントの設定</span><span class="sxs-lookup"><span data-stu-id="c7c31-165">Lync 2010 client settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7c31-166">NoPhoto</span><span class="sxs-lookup"><span data-stu-id="c7c31-166">NoPhoto</span></span></p></td>
<td><p><span data-ttu-id="c7c31-167">なし</span><span class="sxs-lookup"><span data-stu-id="c7c31-167">none</span></span></p></td>
<td><p><span data-ttu-id="c7c31-168"><strong>マイ ピクチャを表示しない</strong></span><span class="sxs-lookup"><span data-stu-id="c7c31-168"><strong>Do not show my picture</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7c31-169">PhotoFromADOnly</span><span class="sxs-lookup"><span data-stu-id="c7c31-169">PhotoFromADOnly</span></span></p></td>
<td><p><span data-ttu-id="c7c31-170">Active Directory</span><span class="sxs-lookup"><span data-stu-id="c7c31-170">Active Directory</span></span></p></td>
<td><p><span data-ttu-id="c7c31-171"><strong>既定のコーポレート ピクチャ</strong></span><span class="sxs-lookup"><span data-stu-id="c7c31-171"><strong>Default corporate picture</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7c31-172">AllPhotos</span><span class="sxs-lookup"><span data-stu-id="c7c31-172">AllPhotos</span></span></p></td>
<td><p><span data-ttu-id="c7c31-173">Web アドレス</span><span class="sxs-lookup"><span data-stu-id="c7c31-173">Web address</span></span></p></td>
<td><p><span data-ttu-id="c7c31-174"><strong>Web アドレスからピクチャを表示する</strong></span><span class="sxs-lookup"><span data-stu-id="c7c31-174"><strong>Show a picture from a web address</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a><span data-ttu-id="c7c31-175">Lync 2010 クライアントが写真を取得する方法</span><span class="sxs-lookup"><span data-stu-id="c7c31-175">How Lync 2010 client gets photos</span></span>

<span data-ttu-id="c7c31-176">Lync 2010 では、ユーザーの写真はアドレス帳サービスによってサーバー上で管理されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-176">In Lync 2010, user photos are managed on the server by the Address Book Service.</span></span> <span data-ttu-id="c7c31-177">Lync クライアントは、最初にサーバーのアドレス帳 Web クエリ (ABWQ) サービスを照会することによってユーザーの写真を取得します。これは、配布リスト展開 web サービスを通じて公開されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-177">Lync client gets user photos by first querying the Address Book Web Query (ABWQ) service on the server, which is exposed through the Distribution List Expansion web service.</span></span> <span data-ttu-id="c7c31-178">クライアントはイメージファイルを受信し、ユーザーのキャッシュにコピーして、表示が必要になるたびにイメージをダウンロードしないようにします。</span><span class="sxs-lookup"><span data-stu-id="c7c31-178">The client receives the image file and then copies it to the user's cache to avoid downloading the image each time it needs to be displayed.</span></span> <span data-ttu-id="c7c31-179">クエリから返される属性値も、ユーザーのキャッシュされたアドレス帳サービスエントリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-179">The attribute values returned from the query are also stored in the cached Address Book Service entry for the user.</span></span> <span data-ttu-id="c7c31-180">アドレス帳サービスは、すべてのキャッシュされたイメージを24時間ごとに削除します。つまり、サーバー上のキャッシュで新しいユーザーイメージが更新されるまでに最大24時間かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c7c31-180">The Address Book Service deletes all cached images every 24 hours, which means that it can take up to 24 hours for new user images to be updated in the cache on the server.</span></span> <span data-ttu-id="c7c31-181">[Update-csaddressbook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)コマンドレットを使用して、キャッシュに強制的に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-181">You can force an update to the cache by using the [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet.</span></span>

<span data-ttu-id="c7c31-182">プレゼンス状態に含まれているユーザーの写真にも、Lync クライアントが使用できる新しい画像があるかどうかを判断するために使用するハッシュ値が関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="c7c31-182">User photos included in Presence status also have an associated hash value that Lync client uses to determine whether there is a newer image available.</span></span> <span data-ttu-id="c7c31-183">プレゼンス状態で使用されるイメージファイルへの変更は、クライアントに自動的に通知されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-183">The client is automatically notified of changes to the image file used in Presence status.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="c7c31-184">GalContacts データベースには写真が格納されていないため、ユーザーの写真をダウンロードすることは、クライアントポリシーの <STRONG>Addressbookavailability</STRONG> 設定 (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-csclientpolicy</A>) に依存しません。</span><span class="sxs-lookup"><span data-stu-id="c7c31-184">Because photos are not stored in the GalContacts.db database, downloading user photos is not dependent on the <STRONG>AddressBookAvailability</STRONG> setting in the client policy (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span></span>



</div>

<span data-ttu-id="c7c31-185">ABWQ サービスへのクエリには、次の属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c7c31-185">The query to the ABWQ service includes the following attributes:</span></span>

  - <span data-ttu-id="c7c31-186">**Photohash**    バイナリ写真データのハッシュ値。現在の写真が変更されたかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-186">**PhotoHash**   The hash value of the binary photo data, and is used to determine whether the current photo has changed.</span></span>

  - <span data-ttu-id="c7c31-187">**PhotoRelPath**    サーバーに保存されているイメージファイルへの相対パス。</span><span class="sxs-lookup"><span data-stu-id="c7c31-187">**PhotoRelPath**   The relative path to the image file stored on the server.</span></span>

  - <span data-ttu-id="c7c31-188">**Photosize**    イメージファイルのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="c7c31-188">**PhotoSize**   The size of the image file, in bytes.</span></span>

  - <span data-ttu-id="c7c31-189">**タイムスタンプ**    イメージファイルが最後にサーバーからダウンロードされ、クライアントキャッシュにコピーされた日時。</span><span class="sxs-lookup"><span data-stu-id="c7c31-189">**TimeStamp**   The date and time at which the image file was last downloaded from the server and copied to the client cache.</span></span>

<span data-ttu-id="c7c31-190">次に、Lync 2010 クライアントは、イメージファイルを取得した後、クエリから返された属性値と、インバンドプロビジョニングからクライアントが受信した属性値を比較して、それらが異なるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c7c31-190">Next, after retrieving the image file, Lync 2010 client compares the attribute values returned from the query against the attribute values received by the client from in-band provisioning to see if they are different.</span></span> <span data-ttu-id="c7c31-191">値が異なる場合、クライアントは、HTTP GET 要求を使用して、サインインしているユーザーのイメージファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="c7c31-191">If the values are different, the client retrieves the image file of the signed-in user with an HTTP GET request.</span></span>

<span data-ttu-id="c7c31-192">また、クライアントは、キャッシュされたバージョンのイメージファイルが作成された時点から、サーバーに対して24時間ごとにサーバーをチェックして、サーバー上の **Photohash** 属性の値とクライアント上の値を比較します。</span><span class="sxs-lookup"><span data-stu-id="c7c31-192">Additionally, the client checks with the server every 24 hours from the time at which the cached version of the image file was created to compare the value of the **PhotoHash** attribute on the server with the value on the client.</span></span> <span data-ttu-id="c7c31-193">値が異なる場合、クライアントはイメージファイルが変更されたことを認識します。</span><span class="sxs-lookup"><span data-stu-id="c7c31-193">If the values are different, the client knows that the image file has changed.</span></span> <span data-ttu-id="c7c31-194">更新されたイメージファイルを取得するために、クライアントは再び ABWQ サービスに対してクエリを実行し、サーバー上のイメージファイルでクライアントキャッシュ内のイメージファイルを更新します。これにより、クライアントキャッシュ内のファイルの **タイムスタンプ** もリセットされます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-194">To obtain the updated image file, the client again queries the ABWQ service to update the image file in the client cache with the image file on the server, which also resets the **TimeStamp** on the file in the client cache.</span></span>

<span data-ttu-id="c7c31-195">以下に、ABWQ サービスへのクエリに対する応答の例を示します。</span><span class="sxs-lookup"><span data-stu-id="c7c31-195">The following is an example response to a query to the ABWQ service:</span></span>
```xml
    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>
```

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a><span data-ttu-id="c7c31-196">Lync 2013 のユーザーの写真</span><span class="sxs-lookup"><span data-stu-id="c7c31-196">User photos in Lync 2013</span></span>

<span data-ttu-id="c7c31-197">Lync 2013 には、ユーザー写真の高解像度画像のサポートが導入されました。</span><span class="sxs-lookup"><span data-stu-id="c7c31-197">Lync 2013 introduced support for high-resolution images for user photos.</span></span> <span data-ttu-id="c7c31-198">Lync 2013 には、ユーザーの写真を Exchange 2013 上のユーザーのメールボックスに保存することもサポートされています。これにより、Lync 2010 に存在する画像の解像度とサイズの制限がなくなります。</span><span class="sxs-lookup"><span data-stu-id="c7c31-198">Lync 2013 also includes support for storing user photos in the user's mailbox on Exchange 2013, which removes the image resolution and size limitations present in Lync 2010.</span></span> <span data-ttu-id="c7c31-199">Lync 2013 のユーザーの写真は最大で648ピクセルで、最大 20 MB のファイルサイズを持つ、648ピクセルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-199">User photos in Lync 2013 can be up to 648 pixels by 648 pixels with a file size of up to 20 MB.</span></span> <span data-ttu-id="c7c31-200">Lync 2013 の高解像度写真は、Exchange 2013 上のユーザーのメールボックスにある必要があり、Lync 2013 クライアントでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c7c31-200">High-resolution photos in Lync 2013 must be located in the user's mailbox on Exchange 2013, and are supported only with Lync 2013 client.</span></span> <span data-ttu-id="c7c31-201">この統合 Exchange との統合により、Lync、Exchange、および SharePoint の2013バージョンに含まれる、Oauth という新しい認証フレームワークが利用されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-201">This integration with Exchange takes advantage of the new authorization framework included in the 2013 versions of Lync, Exchange, and SharePoint called Oauth.</span></span>

<span data-ttu-id="c7c31-202">展開で Exchange 2013 を使用していない場合、ユーザーの写真のサポートは Lync 2010 と同じです。</span><span class="sxs-lookup"><span data-stu-id="c7c31-202">If Exchange 2013 is not used in your deployment, support for user photos is the same as with Lync 2010.</span></span> <span data-ttu-id="c7c31-203">ただし、Lync 2013 クライアントでは、使用する写真を選択するためのユーザーオプションが異なります。</span><span class="sxs-lookup"><span data-stu-id="c7c31-203">However, the user options to choose the photo to use are different in Lync 2013 client.</span></span> <span data-ttu-id="c7c31-204">Lync 2013 クライアントでは、ユーザーは [ **マイピクチャの非表示** ] または [ **マイピクチャの表示**] のどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-204">In Lync 2013 client, users can select either **Hide my picture** or **Show my picture**.</span></span> <span data-ttu-id="c7c31-205">[ **Web サイトから画像を表示** する] オプションは既定では利用できませんが、クライアントポリシーを割り当てることによって有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-205">The option **Show a picture from a website** is not available by default, but can be enabled by assigning a client policy.</span></span>

<div>

## <a name="hide-my-picture"></a><span data-ttu-id="c7c31-206">自分の写真を非表示にする</span><span class="sxs-lookup"><span data-stu-id="c7c31-206">Hide my picture</span></span>

<span data-ttu-id="c7c31-207">ユーザー写真の設定は、Lync 2013 の [ **オプション** ] ダイアログにあります。</span><span class="sxs-lookup"><span data-stu-id="c7c31-207">Settings for user photos are on the **Options** dialog in Lync 2013.</span></span> <span data-ttu-id="c7c31-208">**[自分の画像を表示**しない] を選択すると、lync クライアントにはユーザーの写真は表示されませんが、自分の写真は引き続き lync の外部の連絡先カードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-208">When you choose **Hide my picture**, no user photo is displayed for you in Lync client, but your photo is still displayed on your contact card and outside of Lync.</span></span>

</div>

<div>

## <a name="show-my-picture"></a><span data-ttu-id="c7c31-209">自分の写真を表示する</span><span class="sxs-lookup"><span data-stu-id="c7c31-209">Show my picture</span></span>

<span data-ttu-id="c7c31-210">**[自分の画像を表示**する] オプションを選択すると、ユーザーの写真が lync クライアントおよび lync の会話の他のユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-210">When you choose the **Show my picture** option, your user photo is displayed in your Lync client and to other users in Lync conversations.</span></span> <span data-ttu-id="c7c31-211">使用されているイメージは、AD DS に格納されているものです。</span><span class="sxs-lookup"><span data-stu-id="c7c31-211">The image used is the one stored in AD DS.</span></span>

</div>

<div>

## <a name="show-a-picture-from-a-website"></a><span data-ttu-id="c7c31-212">Web サイトから画像を表示する</span><span class="sxs-lookup"><span data-stu-id="c7c31-212">Show a picture from a website</span></span>

<span data-ttu-id="c7c31-213">[ **Web サイトから画像を表示** する] オプションは、クライアントポリシーを有効にするように設定した後、Lync 2013 で利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="c7c31-213">The **Show picture from a website** option becomes available in Lync 2013 after a client policy is set to enable it.</span></span> <span data-ttu-id="c7c31-214">クライアントバージョンは、 [Lync 累積更新プログラム (2013 年11月](https://go.microsoft.com/fwlink/p/?linkid=509908)) でインストールされた15.0.4535.1002 よりも新しいバージョンである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7c31-214">The client version must be newer than 15.0.4535.1002, which is installed with the [Lync Cumulative Updates: November 2013](https://go.microsoft.com/fwlink/p/?linkid=509908).</span></span> <span data-ttu-id="c7c31-215">クライアントでの変更を確認するには、ユーザーは一度ログアウトしてから再度ログインする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="c7c31-215">Users may need to log out and then back in again to see the changes in the client.</span></span>

<span data-ttu-id="c7c31-216">Lync Server 管理シェルで[set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy を実行することによって、 **web サイトの設定から画像を表示**できるようにクライアントポリシーを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-216">You can set the client policy to enable to **Show picture from a website** setting by running the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy in the Lync Server Management Shell.</span></span> <span data-ttu-id="c7c31-217">次のコマンドレットの例では、展開内のすべてのユーザーに対してグローバルにポリシーを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c7c31-217">The following example cmdlets demonstrate how to set the policy globally for all users in your deployment:</span></span>

   ```powershell
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```powershell
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```powershell
    $po.PolicyEntry.Add($pe)
   ```

   ```powershell
    Set-CsClientPolicy -Instance $po
   ```


<span data-ttu-id="c7c31-218">画像がユーザーのメールボックスにアップロードされると、Exchange によって、クライアントアプリケーションで使用できる画像の低解像度バージョンが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-218">When an image is uploaded to the user’s mailbox, Exchange automatically creates a lower resolution version of the image which can be used in client applications.</span></span> <span data-ttu-id="c7c31-219">ユーザー写真は、AD DS でも更新されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-219">The user photo is also updated in AD DS.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="c7c31-220">AD DS でイメージファイルが更新されると、48 x 48 ピクセルのイメージが作成され、AD DS の thumbnailPhoto に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-220">When an image file is updated in AD DS, a 48 x 48 pixel image is created and used for the thumbnailPhoto in AD DS.</span></span> <span data-ttu-id="c7c31-221">既存のイメージは置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-221">Any existing image is replaced.</span></span> <span data-ttu-id="c7c31-222">そのため、96 x 96 イメージを AD DS に追加した場合は、新しい 48 x 48 イメージで上書きされます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-222">So if you added a 96 x 96 image to AD DS, it will be overwritten with the new 48 x 48 image.</span></span> <span data-ttu-id="c7c31-223">これは、Lync 2010 クライアントを使用して、ユーザーが AD DS からユーザーの写真を取得するので、環境内にユーザーがいることです。</span><span class="sxs-lookup"><span data-stu-id="c7c31-223">This is only important is you have users in your environment using Lync 2010 clients, as those clients will obtain user photos from AD DS.</span></span> <span data-ttu-id="c7c31-224">組織内に Lync 2010 クライアントがある場合は、96 x 96 ピクセルのイメージを、AD DS によって作成されたものと置き換えるようにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-224">You can import 96 x 96 pixel images to replace the ones created by AD DS if you have Lync 2010 clients in your organization.</span></span>



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a><span data-ttu-id="c7c31-225">Lync 2013 でのユーザーの写真のサポート</span><span class="sxs-lookup"><span data-stu-id="c7c31-225">User photo support in Lync 2013</span></span>

<span data-ttu-id="c7c31-226">Lync 2013 では、次の表に示すように、ユーザーの写真に3つの画像解像度がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c7c31-226">In Lync 2013, three image resolutions are supported for user photos as described in the following table.</span></span> <span data-ttu-id="c7c31-227">使用されるイメージは、Lync ユーザーに割り当てられているクライアントポリシー設定によって決まります。</span><span class="sxs-lookup"><span data-stu-id="c7c31-227">The image that is used is determined by the client policy setting assigned to Lync users.</span></span> <span data-ttu-id="c7c31-228">詳細については、このトピックの「クライアントポリシーコマンドレットを使用してユーザーの写真を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7c31-228">See “Managing user’s photo with Client Policy cmdlets” in this topic for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7c31-229">画像解像度 (ピクセル)</span><span class="sxs-lookup"><span data-stu-id="c7c31-229">Image resolution (pixels)</span></span></th>
<th><span data-ttu-id="c7c31-230">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c7c31-230">Application</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7c31-231">48 x 48</span><span class="sxs-lookup"><span data-stu-id="c7c31-231">48 x 48</span></span></p></td>
<td><p><span data-ttu-id="c7c31-232">高解像度の画像が選択されていない場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-232">Used if no higher resolution image is selected</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7c31-233">96 x 96</span><span class="sxs-lookup"><span data-stu-id="c7c31-233">96 x 96</span></span></p></td>
<td><p><span data-ttu-id="c7c31-234">Outlook Web App および Outlook 2013 で使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-234">Used in Outlook Web App and Outlook 2013</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7c31-235">648 x 648</span><span class="sxs-lookup"><span data-stu-id="c7c31-235">648 x 648</span></span></p></td>
<td><p><span data-ttu-id="c7c31-236">Lync 2013 デスクトップクライアントおよび Lync 2013 Web アプリで使用</span><span class="sxs-lookup"><span data-stu-id="c7c31-236">Used in Lync 2013 desktop client and Lync 2013 Web App</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c7c31-237">Exchange 2013 でメールボックスが有効になっているすべてのユーザーは、Outlook Web Access または Lync 2013 クライアントオプションを使用して、高解像度写真を含む別のイメージをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="c7c31-237">Any user with a mailbox enabled in Exchange 2013 can upload a different image, including high-resolution photos, through Outlook Web Access or Lync 2013 client options.</span></span> <span data-ttu-id="c7c31-238">使用するイメージの推奨設定は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c7c31-238">The recommended settings for images used include:</span></span>

  - <span data-ttu-id="c7c31-239">**画像の解像度**    648 x 648 ピクセル</span><span class="sxs-lookup"><span data-stu-id="c7c31-239">**Image Resolution**   648 by 648 pixels</span></span>

  - <span data-ttu-id="c7c31-240">**色の深さ**    24ビット</span><span class="sxs-lookup"><span data-stu-id="c7c31-240">**Color Depth**   24-bit</span></span>

  - <span data-ttu-id="c7c31-241">**画像ファイルのサイズ**    最大 20 MB</span><span class="sxs-lookup"><span data-stu-id="c7c31-241">**Image file size**   up to 20 MB</span></span>

  - <span data-ttu-id="c7c31-242">**ファイル形式**    JPEG</span><span class="sxs-lookup"><span data-stu-id="c7c31-242">**File format**   JPEG</span></span>

<span data-ttu-id="c7c31-243">648ピクセル×648ピクセルの一般的な24ビットの JPEG イメージはファイルサイズが約 240 KB なので、4ユーザーの写真ごとに 1 MB の保存スペースが必要になります。</span><span class="sxs-lookup"><span data-stu-id="c7c31-243">A typical 24-bit JPEG image that is 648 pixels by 648 pixels has a file size of about 240 KB, so 1 MB of storage space is needed for every 4 user photos.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

