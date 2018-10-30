---
title: ハイブリッド接続を設定します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Skype ビジネス サーバーとビジネス オンラインの Skype との間のハイブリッド接続の実装方法の詳細については。
ms.openlocfilehash: a85b899407971ebdad0ac4c46096a6feade3fbcd
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839560"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Skype ビジネス サーバーと Office 365 のハイブリッド接続を設定します。
 
**の概要:** ビジネス オンラインまたはチームの業務サーバーの Skype と Skype との間のハイブリッドの接続を構成する方法の詳細については、このトピックを参照してください。  ハイブリッド接続のオンライン ビジネス チームは、Skype に、オンプレミスのユーザーを移動することでき、クラウド サービスを利用することができます。
  
このトピックの手順を実行する前にする必要があります読んだ[Skype ビジネス サーバーと Office 365 の間のハイブリッドの接続を計画](plan-hybrid-connectivity.md)します。
  
次の表では、Skype をビジネスのハイブリッド接続の構成に必要なタスクの一覧し、詳細については、関連する記事へのリンクが用意されています。
  
|**ステップ**|**説明**|
|:-----|:-----|
|Office 365 テナント アカウントを作成し、オンライン ビジネスの Skype を有効にします。  <br/> |[Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980)のオンライン ビジネスでは、Office 365 と Skype について説明します。  <br/> ご使用の環境で Office 365 を使用する準備ができていることを確認するには、「[システム要件](https://products.office.com/en-US/office-system-requirements)」を参照してください。  <br/> Office 365 のセットアップの詳細については、「[Office 365 の使用を開始](https://go.microsoft.com/fwlink/p/?LinkId=254982)」を参照してください。  <br/> |
|Office 365 テナントに自分のドメインを追加し、所有権を確認  <br/> | Office 365 テナントにドメインを追加して、Office 365 でそのドメインを検証します。 この検証は、ドメインの所有者が自分であることを確認するために必要な手順です。 <br/> Office 365 テナントに自分のドメインを追加するのには[Office 365 にドメインの追加](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)で説明する手順に従います。  <br/> |
|作業中のディレクトリ同期を準備します。  <br/> |作業中のディレクトリ同期処理では、Office 365 と同期して継続的に、オンプレミスの Active Directory を保持します。 これにより、各ユーザー アカウントおよびグループの同期バージョンを作成できるだけでなく、ローカルの Microsoft Exchange Server 環境から Microsoft Exchange Online へのグローバル アドレス一覧 (GAL) の同期を実行できるようになります。 詳細については、 [Azure Active Directory と統合、設置ディレクトリ](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)を参照してください。  <br/>  **重要な:** オンライン ビジネスのユーザーが Skype に移動しない場合でも、設置とオンラインの展開では、組織内のビジネス ユーザー向けのすべての Skype の AD のアカウントを同期する必要があります。 すべてのユーザーを同期しない場合、組織のオンプレミス展開のユーザーとオンライン ユーザーとの間の通信が正常に動作しない可能性があります。           |
| Skype をビジネスのハイブリッドを構成します。 | これは、3 つの手順で構成されます。  <br>1. ビジネス オンラインの Skype で、設置型のエッジ サービスのフェデレーションを構成します。 <br> 2. 共有 SIP アドレス スペースのオンライン ビジネスのテナントは、Skype を構成します。 <br> 3. 必要に応じて認証を構成します。    <br> 詳細については、[ビジネスのハイブリッドの Skype の設定](configure-federation-with-skype-for-business-online.md)を参照してください。
|パイロット ユーザーを移動する  <br/> |準備し、Skype のオンライン ビジネスの環境を構成する手順を完了したら、パイロット ユーザーをオンラインの Office 365 テナントに移行を開始できます。 詳細については、[ビジネス オンラインの Skype への設置型からユーザーを移動](move-users-from-on-premises-to-skype-for-business-online.md)し、[チームを設置型からユーザーを移動する](move-users-from-on-premises-to-Teams.md)を参照してください。  <br/> | 

  