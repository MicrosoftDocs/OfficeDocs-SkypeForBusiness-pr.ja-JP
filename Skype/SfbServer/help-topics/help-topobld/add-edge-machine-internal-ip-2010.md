---
title: エッジ コンピューター内部 IP の追加 (2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 857e2041779efd02007939b7046860cc295cb7b8
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219380"
---
# <a name="add-edge-machine-internal-ip-2010"></a>エッジ コンピューター内部 IP の追加 (2010)

このページを使用して、エッジ サーバーの内部 IP アドレスと完全修飾ドメイン名 (FQDN) を指定します。

- [ **内部 IPv4 アドレス**] に、プールに追加するエッジサーバーの IP アドレスを入力します。

- [ **内部 FQDN**] に、プールに追加するエッジサーバーの完全修飾ドメイン名 (FQDN) を入力します。

指定する FQDN が、サーバーに構成されているコンピューター名と同じである必要があります。 既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。 トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。 そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前で、ドメイン ネーム システム (DNS) サフィックスを構成する必要があります。 コンピューター名への DNS サフィックスの追加の詳細については、「[Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)」を参照してください。


