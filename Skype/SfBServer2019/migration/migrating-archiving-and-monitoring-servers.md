---
title: アーカイブと監視サーバーの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 従来の環境でアーカイブサーバーと監視サーバーを展開した場合、フロントエンドプールを移行した後で、これらのサーバーを Skype for Business Server 2019 環境に展開できます。 ただし、アーカイブと監視の機能が組織にとって重要である場合は、移行前に Skype for Business Server 2019 パイロットプールにアーカイブと監視を追加して、移行プロセス中に機能が利用できるようにする必要があります。
ms.openlocfilehash: 5088f4b4f72ddc083cf2868df893946561eb2469
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813455"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>アーカイブと監視サーバーの移行

従来の環境でアーカイブサーバーと監視サーバーを展開した場合、フロントエンドプールを移行した後で、これらのサーバーを Skype for Business Server 2019 環境に展開できます。 ただし、アーカイブと監視の機能が組織にとって重要である場合は、移行前に Skype for Business Server 2019 パイロットプールにアーカイブと監視を追加して、移行プロセス中に機能が利用できるようにする必要があります。 
  
移行プロセス中にアーカイブと監視機能が必要な場合は、次の点に注意してください。
  
- データのアーカイブと監視は、Skype for Business Server 2019 の展開には移行されません。 従来の環境を廃止する前にバックアップしたデータは、従来の環境でのアクティビティの履歴となります。
    
- 古いバージョンのアーカイブサーバーと監視サーバーは、従来のフロントエンドプールにのみ関連付けることができます。 Skype for Business Server 2019 では、アーカイブと監視はサーバーの役割ではなくなりましたが、Skype for Business Server 2019 フロントエンドプールに統合されたサービスです。
    
- 従来の、Skype for Business Server 2019 の展開が共存する間、古いバージョンのアーカイブサーバーと監視サーバーは、従来のプールに所属しているユーザーのデータを収集します。 Skype for Business Server 2019 でのアーカイブと監視 Skype for Business Server 2019 プールを使用しているユーザーのデータを収集します。
    
    > [!NOTE]
    > 新しい Skype for Business Server 2019 パイロットプールで従来のエッジサーバーを使用している場合、移行のフェーズ中に、古いバージョンのアーカイブサーバーでは、従来のプールに所属していて、Skype for Business でアーカイブされているユーザーのデータを収集し続けることができます。サーバー2019は、Skype for Business Server 2019 プールに所属しているユーザーのためにデータを収集します。 
  
- Skype for Business Server 2019 でのアーカイブと監視に関連して、サードパーティのアーカイブと監視ソリューションを使用している場合は、サードパーティのソリューションを Skype for Business Server 2019 と統合する時期とその方法について、ベンダーにお問い合わせください。
    

