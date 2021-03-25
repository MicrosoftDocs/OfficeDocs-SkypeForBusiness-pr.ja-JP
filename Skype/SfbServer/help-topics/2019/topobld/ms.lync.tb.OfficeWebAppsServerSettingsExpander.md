---
title: Office Web Apps サーバーの設定を編集する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.OfficeWebAppsServerSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7a4b91ff-ca11-4dde-852d-ec51d143968a
ROBOTS: NOINDEX, NOFOLLOW
description: 構成されている Web Apps Server のプロパティOffice編集します。 編集できるプロパティは次のとおりです。
ms.openlocfilehash: 0c5dbff11d6cc2f6b25f3afa77cfe12e1e511a8a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121080"
---
# <a name="edit-office-web-apps-server-settings"></a><span data-ttu-id="27658-104">Office Web Apps サーバーの設定の編集</span><span class="sxs-lookup"><span data-stu-id="27658-104">Edit Office Web Apps Server Settings</span></span>

<span data-ttu-id="27658-105">構成されている Web Apps Server のプロパティOffice編集します。</span><span class="sxs-lookup"><span data-stu-id="27658-105">You edit the properties of the configured Office Web Apps Server.</span></span> <span data-ttu-id="27658-106">編集できるプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="27658-106">The following properties are available to edit:</span></span>

 <span data-ttu-id="27658-107">**Office Web Apps Server FQDN**: このプロパティは、Office Web Apps Server の完全修飾ドメイン名を定義し、ドメイン ネーム システム (DNS) ホスト A または AAAA (IPv6 が使用されている場合) レコードと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27658-107">**Office Web Apps Server FQDN**: This property defines the fully qualified domain name of the Office Web Apps Server and should match a domain name system (DNS) host A or AAAA (if IPv6 is being used) record.</span></span>

 <span data-ttu-id="27658-108">**Office Web Apps Server** 探索 URL : Office Web Apps Server へのクライアント アクセス用の統一リソース ロケーター (URL) では、展開用の内部ネットワーク以外の別のネットワーク 領域にサーバーが配置されている場合は、既定からこのアドレスを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27658-108">**Office Web Apps Server discovery URL**: The uniform resource locator (URL) for client access to the Office Web Apps Server, you may need to edit this address from its default if the server is placed in another network zone other than the internal network for your deployment.</span></span>

<span data-ttu-id="27658-109">このサーバーの展開先が境界ネットワークであるか、または内部展開から境界ネットワーク、信頼性の低いネットワーク、およびインターネットを分離する内部ファイアウォールの外にある他のネットワーク ゾーンである場合は、[**Office Web Apps サーバーは外部ネットワークで展開**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="27658-109">Select the check box **Office Web Apps Server is deployed in an external network** if this server is deployed in your perimeter network or other network zone that is outside of your internal firewall separating the perimeter network, less trusted networks, and the Internet from your internal deployment.</span></span>

![Office Web アプリ設定エキスパンダー](../../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="27658-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="27658-111">See also</span></span>

[<span data-ttu-id="27658-112">会議のコンポーネンツおよびトポロジ</span><span class="sxs-lookup"><span data-stu-id="27658-112">Components and Topologies for Conferencing</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)