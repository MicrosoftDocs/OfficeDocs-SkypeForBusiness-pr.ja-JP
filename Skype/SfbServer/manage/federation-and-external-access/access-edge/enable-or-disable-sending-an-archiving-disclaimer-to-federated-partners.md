---
title: フェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 889716377f89e2657adcd6e32c9077b8124e20c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818358"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="79ed3-102">Skype for Business Server でフェデレーションパートナーへのアーカイブの免責事項の送信を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="79ed3-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="79ed3-103">エッジサーバーを展開して組織のフェデレーションを有効にした時点で、アーカイブの免責事項をフェデレーションパートナーに自動的に送信するかどうかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ed3-103">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="79ed3-104">外部通信をアーカイブする場合は、アーカイブの免責事項の送信を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ed3-104">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="79ed3-105">この設定を変更するには、このトピックの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="79ed3-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="79ed3-106">次の手順では、組織のフェデレーションを既に有効にしていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="79ed3-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="79ed3-107">フェデレーションを有効にする方法について詳しくは、「[リモートユーザーアクセスを有効または無効](enable-or-disable-remote-user-access.md)にする」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="79ed3-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="79ed3-108">フェデレーションパートナーへのアーカイブの免責事項の送信を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="79ed3-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="79ed3-109">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="79ed3-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="79ed3-110">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="79ed3-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="79ed3-111">左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**アクセスエッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79ed3-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="79ed3-112">[**アクセス エッジ構成**] タブで、[**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79ed3-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="79ed3-113">[ **Access Edge 構成の編集**] の [**フェデレーションユーザーとの通信を有効**にする] で、[アーカイブの**免責事項をフェデレーションパートナーに送信**する] チェックボックスをオンまたはオフにして、アーカイブの免責事項の自動送信を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="79ed3-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="79ed3-114">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79ed3-114">Click **Commit**.</span></span>

<span data-ttu-id="79ed3-115">フェデレーションされたユーザーが Skype for Business Server 展開のユーザーと共同作業できるようにするには、フェデレーションされたユーザーアクセスをサポートするために、少なくとも1つの外部アクセスポリシーを構成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ed3-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="79ed3-116">特定のフェデレーションドメインのアクセス制御の詳細については、「許可されている[外部ドメインのサポートを構成する](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79ed3-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="79ed3-117">Windows PowerShell コマンドレットを使用してアーカイブ免責事項を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="79ed3-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="79ed3-118">アーカイブ免責事項の使用は、Windows PowerShell と CsAccessEdgeConfiguration コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="79ed3-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="79ed3-119">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="79ed3-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="79ed3-120">アーカイブの免責事項を有効にするには</span><span class="sxs-lookup"><span data-stu-id="79ed3-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="79ed3-121">アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="79ed3-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="79ed3-122">アーカイブの免責事項を無効にするには</span><span class="sxs-lookup"><span data-stu-id="79ed3-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="79ed3-123">アーカイブについての免責事項を無効にするには、**EnableArchivingDisclaimer** プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="79ed3-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


