---
title: Skype for Business Server で外部ユーザーのアーカイブの免責事項を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: '概要: Skype for Business Server のアーカイブの免責事項を構成する方法については、このトピックをお読みください。'
ms.openlocfilehash: 5901429918d4cf346cbbf9f1fdad6ff4736817ea
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234359"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a><span data-ttu-id="7b17f-103">Skype for Business Server で外部ユーザーのアーカイブの免責事項を構成する</span><span class="sxs-lookup"><span data-stu-id="7b17f-103">Configure archiving disclaimers for external users in Skype for Business Server</span></span>
 
<span data-ttu-id="7b17f-104">**概要:** このトピックでは、Skype for Business Server のアーカイブの免責事項を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7b17f-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server.</span></span>
  
<span data-ttu-id="7b17f-105">組織で外部パートナーとの通信を行う場合は、相手との通信をアーカイブしていることを相手に伝える必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b17f-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="7b17f-106">エッジサーバーを展開して組織のフェデレーションを有効にすると、アーカイブの免責事項を外部パートナーに自動的に送信するかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b17f-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="7b17f-107">この構成を変更する必要がある場合は、Skype for Business Server コントロールパネルまたは Windows PowerShell **CsAccessEdgeConfiguration**コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b17f-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="7b17f-108">コマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="7b17f-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="7b17f-109">外部ユーザーが Skype for Business Server 展開のユーザーと共同作業できるようにするには、外部ユーザーのアクセスをサポートするために、少なくとも1つの外部アクセスポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b17f-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="7b17f-110">詳細については、「組織の XMPP フェデレーションパートナーを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b17f-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="7b17f-111">特定のフェデレーション ドメインのアクセス制御の詳細については、「個別のフェデレーション ドメインごとのアクセス制御」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b17f-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="7b17f-112">コントロール パネルを使用してアーカイブについての免責事項を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="7b17f-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="7b17f-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7b17f-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7b17f-114">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7b17f-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="7b17f-115">左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b17f-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="7b17f-116">[**アクセス エッジ構成**] タブで、[**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b17f-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="7b17f-117">[**アクセス エッジ構成の編集**] の [**フェデレーションとパブリック IM 接続を有効にする**] で、[**フェデレーション パートナーにアーカイブについての免責事項を送信する**] チェック ボックスをオンまたはオフにして、アーカイブについての免責事項の自動送信を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="7b17f-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="7b17f-118">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b17f-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="7b17f-119">Windows PowerShell を使用してアーカイブについての免責事項を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="7b17f-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="7b17f-120">アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="7b17f-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="7b17f-121">アーカイブについての免責事項を無効にするには、**EnableArchivingDisclaimer** プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="7b17f-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


