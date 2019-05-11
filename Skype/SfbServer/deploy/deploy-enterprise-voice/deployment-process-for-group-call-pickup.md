---
title: ビジネス用の Skype でグループを呼び出すのピックアップのための展開プロセス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: 展開プロセスとビジネス サーバーのエンタープライズ VoIP の Skype でグループを呼び出すのピックアップのための手順を実行します。
ms.openlocfilehash: e31d6159296a73af1da112cb3dee2e75cfa55a3e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892602"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>ビジネス用の Skype でグループを呼び出すのピックアップのための展開プロセス
 
展開プロセスとビジネス サーバーのエンタープライズ VoIP の Skype でグループを呼び出すのピックアップのための手順を実行します。
  
グループ コール ピックアップでは、同僚に自分の電話からの着信呼び出しに応答することができます。 
  
 コール ピックアップのグループを使用するコンポーネントが自動的にインストールし、エンタープライズ VoIP を展開するときにフロント エンド サーバーまたは Standard Edition サーバー上で有効になっています。 ただし、ユーザーが使用可能になる前に、コール ピックアップのグループを構成するのには次の手順を使用する必要があります。
  
**グループ通話ピックアップの展開プロセス**

|**段階**|**手順**|**必要なグループおよび役割**|**「展開」のドキュメント**|
|:-----|:-----|:-----|:-----|
|トポロジでは、SEFAUtil ツールを有効にします。|新規 CsTrustedApplicationPool コマンドレットを使用すると、新しい信頼されたアプリケーション プールを作成します。 新規 CsTrustedApplication コマンドレットを使用すると、信頼されたアプリケーションとして、SEFAUtil ツールを指定します。 トポロジを有効にする有効にする CsTopology コマンドレットを実行します。 いない場合に、SEFAUtil ツールのビジネスのサーバーのバージョンの Skype をこの場所からダウンロードし、手順 1 で作成する信頼されたアプリケーション プールをインストールします。 SEFAUtil を実行し、展開内のユーザーの着信の転送設定を表示して、SEFAUtil が適切に実行されることを確認します。 |RTCUniversalServerAdmins  <br/> |[ビジネス用の Skype で SEFAUtil ツールを展開します。](deploy-the-sefautil-tool.md) <br/> [新しい-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[新しい-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[有効にする CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Skype ビジネス 2015年リソース キットのツールのマニュアル](../../management-tools/resource-kit-tools.md)をします。 (Skype ビジネス サーバー用のツールの現在のバージョンを使用する必要がありますが、Lync Server 2013 には、このドキュメントはまだ適用されます)。  <br/> |
|コール パーク オービット テーブルに通話ピックアップの番号範囲を構成する  <br/> |**New-CSCallParkOrbit** コマンドレットを使用して、コール パーク オービット テーブルに通話ピックアップの番号範囲を構成し、通話ピックアップ範囲に **GroupPickup** の種類を割り当てます。  <br/> 既存のダイヤル プランとシームレスに統合するため、番号範囲は、通常、仮想の内線番号のブロックとして構成されます。コール パーク オービット テーブルで Direct Inward Dialing (DID) 番号を範囲番号として指定することはサポートされていません。<br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[作成またはビジネス用の Skype のコール ピックアップのグループ番号の範囲を変更します。](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|ユーザーにコール ピックアップ番号を割り当てるし、ユーザーのグループを呼び出すピックアップを有効にします。  <br/> |リソース キット ツールの SEFAUtil で/enablegrouppickup パラメーターを使用して、コール ピックアップのグループを有効にし、ユーザーの呼び出しのピックアップ番号を割り当てます。  <br/> |-  <br/> |[ユーザーのグループを呼び出すピックアップを有効にして、ビジネスの Skype でグループ番号を割り当てる](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|割り当てられた通話ピックアップ番号をユーザーに通知し、必要な他の番号があるかどうかを確認する  <br/> |ユーザーに対してグループ通話ピックアップを有効にした後、電子メールなどの手段を使ってユーザーに通話ピックアップ グループ番号を伝えます。ユーザーには、ユーザーが監視する可能性があるグループの通話ピックアップ グループ番号を伝えます。ユーザーは、同じグループに属さない他のユーザーの通話も取れるため、複数のグループの通話ピックアップ グループ番号が必要になることもあります。  <br/> |-  <br/> ||
|グループ コール ピックアップ展開を確認します。  <br/> | 通話の発信と取得をテストし、構成が予想どおりに動作することを確認します。少なくとも、以下を確認してください。 <br/>  グループ通話ピックアップを有効にしたユーザーを呼び出して、別のユーザーが呼び出しを受け取るようにします。別のユーザーは、同じグループでも、異なるグループでもよく、グループ通話ピックアップを有効にしている必要はありません。 <br/>  グループ通話ピックアップを有効にしたユーザーを呼び出して、その呼び出しを無視します。 <br/> |-  <br/> ||
   

