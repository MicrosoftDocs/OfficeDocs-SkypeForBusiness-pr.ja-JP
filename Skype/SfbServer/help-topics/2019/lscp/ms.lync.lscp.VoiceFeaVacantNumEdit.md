---
title: 未割り当ての電話番号の新規作成または既存の編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: 未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。
ms.openlocfilehash: 87d83f6285e36abf6b063ba7d6c4d1a93cadc633
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41792165"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="f1b43-104">割り当てられていない電話番号: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="f1b43-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

> [!NOTE]
> <span data-ttu-id="f1b43-105">Skype for business 2019 を Exchange 2013 または Exchange 2016 と統合すると、exchange UM は Skype for Business Server 2019 で利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="f1b43-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="f1b43-106">Exchange 2019 のサポートが変更されたため、クラウドボイスメールとクラウド自動応答機能を利用して、Exchange UM との統合を強調することができます。</span><span class="sxs-lookup"><span data-stu-id="f1b43-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="f1b43-p103">未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f1b43-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1b43-109">割り当てられていない新しい番号範囲の作成または既存の番号範囲の編集が完了したら、[ **OK]** をクリックして、すべての数値範囲を一覧表示する [**未使用の番号**] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="f1b43-109">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="f1b43-110">[未使用の番号 **] ページで**行った変更、または [割り当てられていない番号の**編集** **] ページで**[**コミット**] をクリックするまで、データベースにコミットされません。</span><span class="sxs-lookup"><span data-stu-id="f1b43-110">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="f1b43-111">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="f1b43-111">UI Reference</span></span>

<span data-ttu-id="f1b43-112">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="f1b43-112">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="f1b43-113">**名前**割り当てられていない番号の範囲を示すわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f1b43-113">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="f1b43-114">範囲を保存した後は、この名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f1b43-114">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="f1b43-115">**数値の範囲**最初のフィールドに、割り当てられていない番号の範囲の開始番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="f1b43-115">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="f1b43-116">2番目のフィールドに、範囲の終了番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="f1b43-116">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="f1b43-117">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="f1b43-117">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="f1b43-118">範囲の開始番号または終了番号に内線番号が含まれる場合は、両方の番号が内線番号を含む必要があり、その内線番号は両方の番号で一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1b43-118">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="f1b43-119">数値は正規表現 (tel:) に一致する必要があります。 (\+)?[1-9] \d{0,17}(; ext = [1-9] \d{0,9})?</span><span class="sxs-lookup"><span data-stu-id="f1b43-119">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="f1b43-120">これは、数値が文字列 "tel" で始まる可能性があることを意味します (この文字列は自動的に追加されるように指定していない場合)。プラス記号 (+)、1 ~ 9 桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="f1b43-120">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="f1b43-121">電話番号は最大17桁で、その後に形式の内線番号、内線番号、内線番号が続く場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1b43-121">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="f1b43-122">**アナウンスメントサービス**[**お知らせ**] を選択すると、アナウンスメントアプリケーションは着信通話または**exchange um**を処理して、着信呼び出しを処理します。</span><span class="sxs-lookup"><span data-stu-id="f1b43-122">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="f1b43-123">**アナウンスメントサービス**で**お知らせ**を選択した場合:</span><span class="sxs-lookup"><span data-stu-id="f1b43-123">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="f1b43-124">**転送先サーバーの FQDN**この範囲の未割り当て番号への着信通話を処理するアナウンスメントアプリケーションを実行するアプリケーションサービスのサービス ID を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1b43-124">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="f1b43-125">**お知らせ**この範囲の未割り当ての番号に対して再生するお知らせを選択します。</span><span class="sxs-lookup"><span data-stu-id="f1b43-125">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="f1b43-126">**EXCHANGE UM**で**お知らせサービス**を選択した場合:</span><span class="sxs-lookup"><span data-stu-id="f1b43-126">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="f1b43-127">**自動応答の電話番号**Exchange UM 自動応答の電話番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1b43-127">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="f1b43-128">お知らせ機能と機能の詳細については、計画ドキュメントの「 [Skype For business のアナウンスメントアプリケーションの計画](../../../plan-your-deployment/enterprise-voice-solution/announcement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1b43-128">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="f1b43-129">未使用の番号範囲の使用の詳細については、「操作」のドキュメントの「[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1b43-129">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


