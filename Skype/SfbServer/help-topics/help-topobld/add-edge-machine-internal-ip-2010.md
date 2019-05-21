---
title: エッジ コンピューター内部 IP の追加 (2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: このページを使用して、内部 IP アドレスとエッジサーバーの内部完全修飾ドメイン名 (FQDN) を指定します。
ms.openlocfilehash: 53b4a3d7d7347a151cc34195236f50d492206825
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304717"
---
# <a name="add-edge-machine-internal-ip-2010"></a>エッジ コンピューター内部 IP の追加 (2010)

このページを使用して、内部 IP アドレスとエッジサーバーの内部完全修飾ドメイン名 (FQDN) を指定します。

- [**内部 IPv4 アドレス**] に、プールに追加するエッジサーバーの IP アドレスを入力します。

- [ **INTERNAL FQDN**] に、プールに追加するエッジサーバーの完全修飾ドメイン名 (FQDN) を入力します。

指定する FQDN は、サーバーで構成されているコンピューター名と同じである必要があります。 既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。 トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。 したがって、ドメインに参加していないエッジサーバーとして展開するコンピューターの名前で、ドメインネームシステム (DNS) サフィックスを構成する必要があります。 DNS サフィックスをコンピューター名に追加する方法について詳しくは、「microsoft [Edge サポートのための dns の構成](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)」をご覧ください。


