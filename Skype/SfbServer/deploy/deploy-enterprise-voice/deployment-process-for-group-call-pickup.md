---
title: Skype for Business のグループ通話集配の展開プロセス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Skype for Business Server Enterprise Voice でのグループ通話のピックアップの展開プロセスと手順。
ms.openlocfilehash: 6f46303316bceaae28802ec27fcaea67a8ccaa08
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767470"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Skype for Business のグループ通話集配の展開プロセス
 
Skype for Business Server Enterprise Voice でのグループ通話のピックアップの展開プロセスと手順。
  
グループ通話のピックアップを使用すると、ユーザーは自分の電話から同僚への着信に応答できます。 
  
 グループ通話のピックアップで使用されるコンポーネントは、エンタープライズボイスの展開時に、フロントエンドサーバーまたは Standard Edition サーバーに自動的にインストールされ、有効になります。 ただし、グループ通話のピックアップをユーザーが利用できるようにするには、次の手順を使用する必要があります。
  
**グループ通話ピックアップの展開プロセス**

|**段階**|**手順**|**必要なグループおよび役割**|**「展開」のドキュメント**|
|:-----|:-----|:-----|:-----|
|トポロジで SEFAUtil ツールを有効にする|新しい信頼できるアプリケーションプールを作成するには、CsTrustedApplicationPool コマンドレットを使用します。 SEFAUtil ツールを信頼できるアプリケーションとして指定するには、CsTrustedApplication コマンドレットを使用します。 Enable-CsTopology コマンドレットを実行して、トポロジを有効にします。 まだインストールしていない場合は、この場所から Skype for Business Server バージョンの SEFAUtil ツールをダウンロードして、手順1で作成した信頼されたアプリケーションプールにインストールします。 SEFAUtil を実行し、展開内のユーザーの着信の転送設定を表示して、SEFAUtil が適切に実行されることを確認します。 |RTCUniversalServerAdmins  <br/> |[Skype for Business で SEFAUtil ツールを展開する](deploy-the-sefautil-tool.md) <br/> [新規-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[新規-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[有効にする-CsTopology テクノロジー](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Skype For Business Server 2015 リソースキットツールのドキュメント](../../management-tools/resource-kit-tools.md)。 (Skype for Business Server の場合は、現在のバージョンのツールを使用する必要がありますが、Lync Server 2013 からのこのドキュメントは引き続き適用されます)。  <br/> |
|コール パーク オービット テーブルに通話ピックアップの番号範囲を構成する  <br/> |**New-CSCallParkOrbit** コマンドレットを使用して、コール パーク オービット テーブルに通話ピックアップの番号範囲を構成し、通話ピックアップ範囲に **GroupPickup** の種類を割り当てます。  <br/> 既存のダイヤル プランとシームレスに統合するため、番号範囲は、通常、仮想の内線番号のブロックとして構成されます。コール パーク オービット テーブルで Direct Inward Dialing (DID) 番号を範囲番号として指定することはサポートされていません。<br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business のグループ通話集配の番号範囲を作成または変更する](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|通話集配番号をユーザーに割り当てて、ユーザーに対してグループ通話のピックアップを有効にする  <br/> |SEFAUtil リソースキットツールの/enablegrouppickup パラメーターを使用して、グループ通話のピックアップを有効にし、ユーザーに通話の集配番号を割り当てることができます。  <br/> |-  <br/> |[Skype for Business でユーザーのグループ通話のピックアップを有効にし、グループ番号を割り当てる](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|割り当てられた通話ピックアップ番号をユーザーに通知し、必要な他の番号があるかどうかを確認する  <br/> |ユーザーに対してグループ通話ピックアップを有効にした後、電子メールなどの手段を使ってユーザーに通話ピックアップ グループ番号を伝えます。ユーザーには、ユーザーが監視する可能性があるグループの通話ピックアップ グループ番号を伝えます。ユーザーは、同じグループに属さない他のユーザーの通話も取れるため、複数のグループの通話ピックアップ グループ番号が必要になることもあります。  <br/> |-  <br/> ||
|グループ通話の集配の展開を確認する  <br/> | 通話の発信と取得をテストし、構成が予想どおりに動作することを確認します。少なくとも、以下を確認してください。 <br/>  グループ通話ピックアップを有効にしたユーザーを呼び出して、別のユーザーが呼び出しを受け取るようにします。別のユーザーは、同じグループでも、異なるグループでもよく、グループ通話ピックアップを有効にしている必要はありません。 <br/>  グループ通話ピックアップを有効にしたユーザーを呼び出して、その呼び出しを無視します。 <br/> |-  <br/> ||
   

