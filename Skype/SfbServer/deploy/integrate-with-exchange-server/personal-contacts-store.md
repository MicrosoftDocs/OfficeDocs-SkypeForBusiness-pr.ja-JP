---
title: Lync 2010 クライアント コンピューターの個人用連絡先ストアを構成します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/29/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: '概要: は、レガシ クライアントで使用されている個人用連絡先ストアを構成します。'
ms.openlocfilehash: 4afb40f57043988768118a0b83c0afe7e9df0028
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216656"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a><span data-ttu-id="45a75-103">Lync 2010 クライアント コンピューターの個人用連絡先ストアを構成します。</span><span class="sxs-lookup"><span data-stu-id="45a75-103">Configure the personal contacts store on Lync 2010 client computers</span></span>
  
<span data-ttu-id="45a75-104">ビジネス サーバー 2015 2016 の Exchange Server や Exchange Server 2013 の Skype を統合する場合は、クライアントによって使用される個人用の連絡先ストアを構成してください。</span><span class="sxs-lookup"><span data-stu-id="45a75-104">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store used by the clients.</span></span> <span data-ttu-id="45a75-105">具体的には、Skype をビジネスで個人の連絡先ストアとして Exchange を使用し、同時に、ユーザーは、その判断をオーバーライドできないことを確認しますを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45a75-105">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="45a75-106">そのためには、各クライアント コンピューターでレジストリ値を作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="45a75-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="45a75-107">次の手順は、Lync 2010 クライアントを使用するクライアントに必要なまたはそれ以前ではのみです。</span><span class="sxs-lookup"><span data-stu-id="45a75-107">The following procedure is only necessary for clients using the Lync 2010 client or earlier.</span></span> <span data-ttu-id="45a75-108">Lync 2013 クライアントとビジネス クライアント用のすべての Skype は、連絡先ストアの設定を上書きすることはありません。</span><span class="sxs-lookup"><span data-stu-id="45a75-108">The Lync 2013 client and all Skype for Business clients will not have the option of overriding the contact store settings.</span></span>
  
<span data-ttu-id="45a75-109">1 台のコンピューターでこの値を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="45a75-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="45a75-110">クライアント コンピューターで [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45a75-110">On the client computer, click **Start** and then click **Run**.</span></span>
2. <span data-ttu-id="45a75-111">[**ファイル名を指定して実行**] ダイアログ ボックスで「regedit」と入力して、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="45a75-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
3. <span data-ttu-id="45a75-112">レジストリ エディターで、[**HKEY_LOCAL_MACHINE**]、[**Software**]、[**Policies**]、[**Microsoft**]、[**Communicator**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="45a75-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
4. <span data-ttu-id="45a75-113">[**Communicator**] を右クリックし、[**新規**] をポイントし、[**DWORD (32 ビット) 値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45a75-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
5. <span data-ttu-id="45a75-114">新しい値を作成した後に「PersonalContactStoreOverride」と入力し、Enter キーを押して値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="45a75-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
6. <span data-ttu-id="45a75-115">PersonalContactStoreOverride の値が 0 に設定されていることを確認し、レジストリ エディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="45a75-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="45a75-116">複数のコンピューターでこれと同じ変更をする必要がある場合は、カスタム グループ ポリシー オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="45a75-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="45a75-117">Windows 10 でこれを行う方法の詳細については、[グループ ポリシー オブジェクトを作成する](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45a75-117">For details on doing this in Windows 10, see the [Create a Group Policy Object](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) article.</span></span>
  
