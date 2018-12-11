---
title: フェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 3e076e1044a65c45a8fc72d0e7d54369d4c3196f
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222780"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="7db41-102">ビジネス サーバーの Skype でのフェデレーション パートナーにアーカイブについての免責事項の送信を無効にするを有効または</span><span class="sxs-lookup"><span data-stu-id="7db41-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="7db41-103">時に、エッジ サーバーの展開し、フェデレーションを有効になっている組織では、必要がありますが指定されて自動的にフェデレーション パートナーにアーカイブについての免責事項を送信するかどうか。</span><span class="sxs-lookup"><span data-stu-id="7db41-103">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="7db41-104">外部通信をアーカイブする場合は、アーカイブの免責事項の送信を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7db41-104">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="7db41-105">その構成を変更するのにはこのトピックの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="7db41-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="7db41-106">次の手順では、組織のフェデレーションが既に有効にことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="7db41-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="7db41-107">フェデレーションを有効にする方法の詳細[を有効にするかリモート ユーザー アクセスを無効にする](enable-or-disable-remote-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7db41-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="7db41-108">有効にするか、フェデレーション パートナーへのアーカイブの免責事項の送信を無効にするには</span><span class="sxs-lookup"><span data-stu-id="7db41-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="7db41-109">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7db41-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7db41-110">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="7db41-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7db41-111">左側のナビゲーション ・ バーで [**外部ユーザー アクセス**] をクリックして、[**アクセス エッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7db41-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="7db41-112">[**アクセス エッジ構成**] タブで、[**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7db41-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7db41-113">**アクセス エッジ構成の編集**、**フェデレーション ユーザーとの通信を有効にする**には、オンまたはオフに、**アーカイブ、フェデレーション パートナーへの免責事項を送信**するチェック ボックスを有効にするか、アーカイブを自動的に送信を無効にします。免責事項です。</span><span class="sxs-lookup"><span data-stu-id="7db41-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="7db41-114">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7db41-114">Click **Commit**.</span></span>

<span data-ttu-id="7db41-115">フェデレーション ユーザーにビジネスのサーバーの展開に、Skype のユーザーと共同作業を有効にするには、必要がありますもしているフェデレーション ユーザー アクセスをサポートするために少なくとも 1 つの外部アクセス ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="7db41-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="7db41-116">特定のフェデレーション ドメインのアクセスを制御する方法の詳細は、[許可された外部ドメインのサポートを構成する](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7db41-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7db41-117">有効にするか、Windows PowerShell コマンドレットを使用して、アーカイブの免責事項を無効にします。</span><span class="sxs-lookup"><span data-stu-id="7db41-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="7db41-118">アーカイブについての免責事項の使用は、Windows PowerShell とセット CsAccessEdgeConfiguration コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="7db41-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="7db41-119">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7db41-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="7db41-120">アーカイブについての免責事項を有効にするには</span><span class="sxs-lookup"><span data-stu-id="7db41-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="7db41-121">アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="7db41-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="7db41-122">アーカイブについての免責事項を無効にするには</span><span class="sxs-lookup"><span data-stu-id="7db41-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="7db41-123">アーカイブについての免責事項を無効にするには、**EnableArchivingDisclaimer** プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="7db41-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


