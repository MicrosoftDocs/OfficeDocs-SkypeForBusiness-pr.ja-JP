---
title: エッジ コンピューター内部 IP の追加 (2010)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: このページを使用して、エッジ サーバーの内部 IP アドレスと完全修飾ドメイン名 (FQDN) を指定します。
ms.openlocfilehash: 51ab7e117892efbbbd7fd16a27b3f06b599297b9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120950"
---
# <a name="add-edge-machine-internal-ip-2010"></a>エッジ コンピューター内部 IP の追加 (2010)

このページを使用して、エッジ サーバーの内部 IP アドレスと完全修飾ドメイン名 (FQDN) を指定します。

- [ **内部 IPv4 アドレス]** に、プールに追加するエッジ サーバーの IP アドレスを入力します。

- [ **内部 FQDN]** に、プールに追加するエッジ サーバーの完全修飾ドメイン名 (FQDN) を入力します。

指定する FQDN が、サーバーに構成されているコンピューター名と同じである必要があります。 既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。 トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。 そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前で、ドメイン ネーム システム (DNS) サフィックスを構成する必要があります。 コンピューター名への DNS サフィックスの追加の詳細については、「[Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)」を参照してください。