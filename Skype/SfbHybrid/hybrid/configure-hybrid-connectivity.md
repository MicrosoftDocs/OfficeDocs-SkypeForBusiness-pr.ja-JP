---
title: ハイブリッド接続の構成|2019 Skype for Business Server接続の展開
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: ハイブリッド接続を実装する手順は、Skype for Business ServerとTeams。
ms.openlocfilehash: 832aa989d8f698ac939dbf522476fb9dd6bfb2b8
ms.sourcegitcommit: 3f1635d1915561798ea764c3e33d7db55f7e49da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2021
ms.locfileid: "53574062"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>デバイスとデバイス間のハイブリッド接続Skype for Business Server構成Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**概要:** このトピックでは、ハイブリッド接続を構成する方法について説明します。Skype for Business ServerとTeams。  ハイブリッド接続を使用すると、オンプレミス のユーザーをクラウド サービスにTeams、ユーザーがクラウド サービスを利用できます。
  
このトピックの手順を実行する前に、「ハイブリッド接続を計画する」を参照Skype for Business Server[と](plan-hybrid-connectivity.md)Teams。
  
次の表に、ハイブリッド接続を構成するためにSkype for Businessタスクの一覧と、関連する記事へのリンクを示します。
  
|手順|説明|
|:-----|:-----|
|ユーザーのテナント アカウントを作成Microsoft 365   <br/> |詳細については、「Microsoft 365」[を参照Microsoft 365。](https://go.microsoft.com/fwlink/p/?LinkId=254980)  <br/> 環境の準備が完了していることを確認するには、「システムMicrosoft 365」[を参照してください](https://products.office.com/office-system-requirements)。  <br/> ユーザー設定の詳細については、「Microsoft 365[の概要」を参照Microsoft 365。](https://go.microsoft.com/fwlink/p/?LinkId=254982)  <br/> |
|ドメインを組織に追加Microsoft 365所有権を確認する  <br/> | ドメインを組織に追加しMicrosoft 365手順に従ってドメインを検証する必要Microsoft 365。 これは、自分がドメインの所有者である必要があります。 <br/> ドメインを組織の組織にMicrosoft 365するには、「ドメインを組織に追加する」で説明されている[手順に従](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)Microsoft 365。  <br/> |
|Active Directory 同期のセットアップ  <br/> |Active Directory の同期により、オンプレミスの Active Directory は継続的に同期され、Microsoft 365。 これにより、各ユーザー アカウントとグループの同期バージョンを作成できます。  <br/> <br> **重要:** 組織内のすべての Skype for Business ユーザーの AD アカウントを、オンプレミス展開とオンライン展開の間で同期する必要があります (ユーザーが Teams に移動されていない場合でも)。 すべてのユーザーを同期しない場合は、組織内のオンプレミスユーザーとオンライン ユーザー間の通信が期待通りには機能しない場合があります。 詳細については[、「Configure Azure AD Connect ハイブリッド環境」を参照してください](configure-azure-ad-connect.md)。         |
| Skype for Business ハイブリッドの構成 | 次の 3 つの基本的な手順があります。 <br><br> 1. オンプレミス環境を構成して、サーバーとフェデレーションMicrosoft 365。 <br> 2. オンプレミス環境を構成して、Microsoft 365を信頼し、共有 SIP アドレス空間を有効Microsoft 365。<br> 3. 組織で共有 SIP アドレス空間Microsoft 365します。 <br><br> また、オンプレミス環境Exchange場合は、オンプレミス環境とオンライン環境の間Exchange OAuth を構成することもできます。 <br> <br>詳細については、「Configure [Skype for Business ハイブリッド」を参照してください](configure-federation-with-skype-for-business-online.md)。
|パイロット ユーザーの移動  <br/> |ユーザーの環境を準備して構成する手順を完了したら、Teamsユーザーをオンラインの組織に移動Microsoft 365できます。 詳細については、「ユーザーを[オンプレミスからユーザーに移動する」を参照](move-users-from-on-premises-to-Teams.md)Teams。  <br/> |
