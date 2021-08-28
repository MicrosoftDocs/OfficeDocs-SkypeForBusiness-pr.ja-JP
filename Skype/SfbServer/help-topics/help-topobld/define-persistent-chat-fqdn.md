---
title: 常設チャットの FQDN の定義
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: 新しい常設チャット サーバーまたは常設チャット サーバー プールを作成するには、[新しい常設チャット プールの定義] ウィザードを使用します。 [複数のコンピューター プール] または [単一のコンピューター プール] を選択します。 1 つのコンピューター プールを選択し、後で複数のコンピューター プールが必要な場合は、1 つのコンピューター プールを削除してから、複数のコンピューター プールを定義する必要があります。
ms.openlocfilehash: 2136d740a451670fe01d3123c48c63f3d7de0cc1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622459"
---
# <a name="define-persistent-chat-fqdn"></a>常設チャットの FQDN の定義
 
新しい常設チャット サーバーまたは常設チャット サーバー プールを作成するには、[新しい常設チャット プールの定義] ウィザード **を使用** します。 [複数のコンピューター プール **] または [単一** の **コンピューター プール] を選択します**。 1 つのコンピューター プールを選択し、後で複数のコンピューター プールが必要な場合は、1 つのコンピューター プールを削除してから、複数のコンピューター プールを定義する必要があります。
  
常設チャット サーバーまたは **常設チャット サーバー** プールのプール FQDN も定義する必要があります。 1 台のコンピューター プールの完全修飾ドメイン名 (FQDN) は、単一サーバー プールを構成するコンピューターの FQDN と同じにする必要があります。 複数のコンピューター プールの場合、FQDN は、この複数のコンピューター プールを表す名前で、ホスト A (および IPv6 が使用されている場合は AAAA) レコードによって DNS で定義されている必要があります。
  
## <a name="see-also"></a>関連項目

[2015 年の常設チャット サーバー Skype for Business Serverする](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[常設チャット サーバーを 2015 Skype for Business Serverトポロジに追加する](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
