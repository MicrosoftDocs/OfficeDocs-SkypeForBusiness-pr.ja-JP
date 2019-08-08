---
title: Lync 2010 クライアントコンピューターで個人用連絡先ストアを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: '概要: レガシクライアントで使用される個人用連絡先ストアを構成します。'
ms.openlocfilehash: 26352517ea31b5556784f6f1ea8d1ce661cfe184
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244194"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a><span data-ttu-id="5be05-103">Lync 2010 クライアントコンピューターで個人用連絡先ストアを構成する</span><span class="sxs-lookup"><span data-stu-id="5be05-103">Configure the personal contacts store on Lync 2010 client computers</span></span>
  
<span data-ttu-id="5be05-104">Skype for Business Server 2015 と Exchange Server 2016、または Exchange Server 2013 を統合する場合は、クライアントで使用する個人用連絡先ストアを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5be05-104">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store used by the clients.</span></span> <span data-ttu-id="5be05-105">特に、Skype for Business が個人の連絡先ストアとして Exchange を使用するように構成し、同時にユーザーがその決定を上書きできないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5be05-105">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="5be05-106">そのためには、各クライアント コンピューターでレジストリ値を作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="5be05-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5be05-107">次の手順は、Lync 2010 クライアントまたはそれ以前のバージョンを使用しているクライアントに対してのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="5be05-107">The following procedure is only necessary for clients using the Lync 2010 client or earlier.</span></span> <span data-ttu-id="5be05-108">Lync 2013 クライアントとすべての Skype for Business クライアントには、連絡先ストアの設定を上書きするオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="5be05-108">The Lync 2013 client and all Skype for Business clients will not have the option of overriding the contact store settings.</span></span>
  
<span data-ttu-id="5be05-109">1 台のコンピューターでこの値を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5be05-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="5be05-110">クライアント コンピューターで [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5be05-110">On the client computer, click **Start** and then click **Run**.</span></span>
2. <span data-ttu-id="5be05-111">[**ファイル名を指定して実行**] ダイアログ ボックスで「regedit」と入力して、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5be05-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
3. <span data-ttu-id="5be05-112">レジストリ エディターで、[**HKEY_LOCAL_MACHINE**]、[**Software**]、[**Policies**]、[**Microsoft**]、[**Communicator**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="5be05-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
4. <span data-ttu-id="5be05-113">[**Communicator**] を右クリックし、[**新規**] をポイントし、[**DWORD (32 ビット) 値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5be05-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
5. <span data-ttu-id="5be05-114">新しい値を作成した後に「PersonalContactStoreOverride」と入力し、Enter キーを押して値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="5be05-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
6. <span data-ttu-id="5be05-115">PersonalContactStoreOverride の値が 0 に設定されていることを確認し、レジストリ エディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5be05-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="5be05-116">複数のコンピューターでこれと同じ変更をする必要がある場合は、カスタム グループ ポリシー オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5be05-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="5be05-117">Windows 10 での操作の詳細については、「[グループポリシーオブジェクトを作成する](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5be05-117">For details on doing this in Windows 10, see the [Create a Group Policy Object](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) article.</span></span>
  
