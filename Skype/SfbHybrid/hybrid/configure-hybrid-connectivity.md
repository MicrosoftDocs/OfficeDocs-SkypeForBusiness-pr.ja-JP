---
title: ハイブリッド接続を構成する |Skype for Business Server 2019 connect の展開
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
description: Skype for Business Server と Skype for business Online 間のハイブリッド接続を実装するための手順。
ms.openlocfilehash: 0c4b2f716e906e30dd45b2750cfe5487868ce6df
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780096"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Skype for Business Server と Office 365 の間のハイブリッド接続を構成する

**概要:** このトピックでは、Skype for Business Server と Teams または Skype for Business Online 間のハイブリッド接続を構成する方法について説明します。  ハイブリッド接続を使用すると、オンプレミスのユーザーを Teams または Skype for business Online に移動し、ユーザーがクラウドサービスを利用できるようになります。
  
このトピックの手順を実行する前に、「 [Skype For Business Server と Office 365 の間のハイブリッド接続を計画](plan-hybrid-connectivity.md)する」を参照してください。
  
次の表に、Skype for Business のハイブリッド接続を構成するために必要なタスクと、関連する記事へのリンクを示します。詳細については、「」を参照してください。
  
|手順|説明|
|:-----|:-----|
|Office 365 のテナントアカウントを作成する   <br/> |Office [365](https://go.microsoft.com/fwlink/p/?LinkId=254980)の office 365 について説明します。  <br/> 環境で Office 365 の準備が整っていることを確認するには、[システム要件](https://products.office.com/office-system-requirements)を参照してください。  <br/> Office 365 のセットアップの詳細については、「 [office 365 の](https://go.microsoft.com/fwlink/p/?LinkId=254982)概要」を参照してください。  <br/> |
|Office 365 組織にドメインを追加し、所有権を確認する  <br/> | Office 365 組織にドメインを追加してから、Office 365 でドメインを検証する手順を実行する必要があります。 これは、ドメインの所有者であることを確認するためのものです。 <br/> Office 365 組織にドメインを追加するには、「 [add a domain To office 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)」に記載されている手順に従います。  <br/> |
|Active Directory 同期をセットアップする  <br/> |Active Directory 同期では、オンプレミスの Active Directory が Office 365 と継続的に同期されます。 これにより、各ユーザーアカウントおよびグループの同期バージョンを作成できます。  <br/> <br> **重要:** ユーザーが Teams または Skype for business Online に移動されていない場合でも、組織内のすべての Skype for Business ユーザーの AD アカウントをオンプレミスの展開とオンライン展開の間で同期する必要があります。 すべてのユーザーを同期しない場合は、組織内のオンプレミスのユーザーとオンラインユーザーとの間の通信が期待どおりに機能しないことがあります。 詳細については、「 [AZURE AD Connect のハイブリッド環境用の構成](configure-azure-ad-connect.md)」を参照してください。         |
| Skype for Business ハイブリッドの構成 | 次の 3 つの基本的な手順があります。 <br><br> 1. Office 365 とフェデレーションするようにオンプレミス環境を構成します。 <br> 2. Office 365 を信頼するようにオンプレミス環境を構成し、Office 365 で共有 SIP アドレススペースを有効にします。<br> 3. Office 365 組織の共有 SIP アドレススペースを有効にします。 <br><br> また、オンプレミスの Exchange を使用している場合は、Exchange オンプレミス環境と Skype for Business 環境の間で OAuth を構成することができます。 <br> <br>詳細については、「 [Skype For business ハイブリッドの構成](configure-federation-with-skype-for-business-online.md)」を参照してください。
|パイロットユーザーを移動する  <br/> |Teams または Skype for Business Online の環境を準備および構成する手順を完了したら、パイロットユーザーのオンライン Office 365 組織への移行を開始できます。 詳細については、「[ユーザーをオンプレミスから Skype For Business Online に移動する](move-users-from-on-premises-to-skype-for-business-online.md)」と「[オンプレミスから Teams にユーザーを移動](move-users-from-on-premises-to-Teams.md)する」を参照してください。  <br/> |