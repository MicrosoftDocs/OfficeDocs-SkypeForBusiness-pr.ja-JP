---
title: 割り当てられていない電話番号を新規作成または既存の編集
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: 未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。
ms.openlocfilehash: 6df9574bb6d999e4800c727f6cbabe0aa68818e9
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244196"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="709b0-104">割り当てられていない電話番号: 新規作成または既存の編集</span><span class="sxs-lookup"><span data-stu-id="709b0-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

> [!NOTE]
> <span data-ttu-id="709b0-105">Exchange UM のまま Skype で利用可能なビジネス サーバー 2019 の Exchange 2013 または Exchange 2016 2019 のビジネス用の Skype を統合する場合です。</span><span class="sxs-lookup"><span data-stu-id="709b0-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="709b0-106">2019 の Exchange でのサポートの変更により、Exchange UM の統合は、ボイスメールのクラウドとクラウドの自動応答の機能のための emphasised ことです。</span><span class="sxs-lookup"><span data-stu-id="709b0-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasised in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="709b0-p103">未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。</span><span class="sxs-lookup"><span data-stu-id="709b0-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="709b0-109">新しい割り当てられていない番号範囲を作成または既存の編集が終了したら、すべての数値の範囲を示す**番号が割り当てられていない**ページに戻るには **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="709b0-109">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="709b0-110">**新しい未割り当ての番号範囲**] ページまたは **[割り当てられていない番号 Rage の編集**ページに加えた変更は、[**割り当てられていない番号**] ページ**のすべてのコミット**をクリックするまでにはデータベースにコミットされません。</span><span class="sxs-lookup"><span data-stu-id="709b0-110">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="709b0-111">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="709b0-111">UI Reference</span></span>

<span data-ttu-id="709b0-112">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="709b0-112">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="709b0-113">**名**未使用の番号の範囲を識別するわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="709b0-113">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="709b0-114">範囲を保存すると、この名前は変更できません。</span><span class="sxs-lookup"><span data-stu-id="709b0-114">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="709b0-115">**番号の範囲**最初のフィールドに割り当てられていない番号の範囲の開始番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="709b0-115">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="709b0-116">2 番目のフィールドには、範囲の終了番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="709b0-116">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="709b0-117">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="709b0-117">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="709b0-118">範囲の開始番号または終了番号に内線番号が含まれる場合は、両方の番号が内線番号を含む必要があり、その内線番号は両方の番号で一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="709b0-118">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="709b0-119">番号が正規表現に一致する必要があります (tel:) ? (\+) ? [1-9] \d{0,17}(; ext = [1-9] \d{0,9}) ?。</span><span class="sxs-lookup"><span data-stu-id="709b0-119">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="709b0-120">つまり、番号の先頭に文字列 tel: (その文字列を指定しない場合に自動的に追加)、プラス記号 (+) と数字の 1 9 から。</span><span class="sxs-lookup"><span data-stu-id="709b0-120">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="709b0-121">電話番号が最大 17 桁にすることができ、拡張した形式で続いて ext = 内線番号の後にします。</span><span class="sxs-lookup"><span data-stu-id="709b0-121">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="709b0-122">**サービスのお知らせ****発表**のお知らせアプリケーションが着信呼び出しを処理するか、 **Exchange UM**を Exchange UM 自動応答着信呼び出しを処理するを選択します。</span><span class="sxs-lookup"><span data-stu-id="709b0-122">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="709b0-123">**お知らせサービス**の**お知らせ**を選択した場合。</span><span class="sxs-lookup"><span data-stu-id="709b0-123">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="709b0-124">**宛先サーバーの FQDN**この範囲の割り当てられていない番号への着信呼び出しを処理するアナウンス アプリケーションを実行するアプリケーション サービスのサービス ID を選択します。</span><span class="sxs-lookup"><span data-stu-id="709b0-124">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="709b0-125">**お知らせ**この割り当てられていない番号の範囲を再生するアナウンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="709b0-125">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

-  <span data-ttu-id="709b0-126">**Exchange UM** **サービスのお知らせ**を選択した場合。</span><span class="sxs-lookup"><span data-stu-id="709b0-126">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="709b0-127">**自動応答の電話番号**Exchange UM 自動応答の電話番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="709b0-127">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="709b0-128">発表の特徴と機能についての詳細は、計画ドキュメントに[ビジネス用の Skype で知らせアプリケーションの計画](../../../plan-your-deployment/enterprise-voice-solution/announcement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="709b0-128">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="709b0-129">割り当てられていない番号範囲の操作についての詳細は、操作マニュアル[を構成するルーティングの割り当てられていない電話番号](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="709b0-129">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


