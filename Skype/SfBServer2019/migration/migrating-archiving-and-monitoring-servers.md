---
title: アーカイブおよび監視サーバーの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 従来の環境でアーカイブサーバーと監視サーバーを展開した場合は、フロントエンドプールを移行した後に、これらのサーバーを Skype for Business Server 2019 環境に展開できます。 ただし、アーカイブおよび監視機能が組織にとって重要な場合は、移行の前に Skype for Business Server 2019 パイロットプールにアーカイブと監視を追加して、移行プロセス中に機能を利用できるようにする必要があります。
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752669"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>アーカイブおよび監視サーバーの移行

従来の環境でアーカイブサーバーと監視サーバーを展開した場合は、フロントエンドプールを移行した後に、これらのサーバーを Skype for Business Server 2019 環境に展開できます。 ただし、アーカイブおよび監視機能が組織にとって重要な場合は、移行の前に Skype for Business Server 2019 パイロットプールにアーカイブと監視を追加して、移行プロセス中に機能を利用できるようにする必要があります。 
  
移行プロセスで、アーカイブ機能と監視機能が必要な場合は、以下の点を考慮してください。
  
- アーカイブデータと監視データは、Skype for Business Server 2019 展開には移動されません。 従来の環境を使用停止にする前にバックアップしたデータは、従来の環境でのアクティビティの履歴になります。
    
- 古いバージョンのアーカイブサーバーと監視サーバーは、従来のフロントエンドプールにのみ関連付けることができます。 Skype for Business Server 2019 では、アーカイブと監視はサーバーの役割ではなくなりますが、サービスが Skype for Business Server 2019 フロントエンドプールに統合されています。
    
- 従来の、または Skype for Business Server 2019 の展開が共存している間、従来のバージョンのアーカイブサーバーと監視サーバーは、従来のプールに所属するユーザーのためにデータを収集します。 Skype for business server 2019 でのアーカイブと監視 Skype for business Server 2019 プールに所属するユーザーのためにデータを収集します。
    
    > [!NOTE]
    > 移行のフェーズでは、新しい Skype for business Server 2019 パイロットプールで従来のエッジサーバーを使用していても、従来のバージョンのアーカイブサーバーは従来のプールに所属しているユーザーのデータ収集を続行し、skype for business server 2019 プールに所属するユーザーのために Skype for business Server 2019 のアーカイブデータを収集します。 
  
- サードパーティ製のアーカイブおよび監視ソリューションを Skype for business Server 2019 のアーカイブおよび監視と組み合わせて使用する場合は、サードパーティ製ソリューションと Skype for Business Server 2019 を統合する時期と方法についてベンダーにお問い合わせください。
    

