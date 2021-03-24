---
title: Skype for Business でのグループ通話ピックアップの展開プロセス
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype for Business Server でのグループ通話ピックアップの展開プロセスとエンタープライズ VoIP。
ms.openlocfilehash: 44f161b72661bb6bdaf52c88448df23546439be1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105793"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Skype for Business でのグループ通話ピックアップの展開プロセス
 
Skype for Business Server でのグループ通話ピックアップの展開プロセスとエンタープライズ VoIP。
  
グループ通話ピックアップを使用すると、ユーザーは自分の電話から同僚への着信通話に応答できます。 
  
 グループ通話ピックアップで使用するコンポーネントは、展開時にフロントエンド サーバーまたは Standard Edition サーバーに自動的にインストールされエンタープライズ VoIP。 ただし、グループ通話ピックアップをユーザーが利用するには、次の手順を使用してグループ通話ピックアップを構成する必要があります。
  
**グループ通話ピックアップの展開プロセス**

|**フェーズ**|**手順**|**必要なグループおよび役割**|**展開のドキュメント**|
|:-----|:-----|:-----|:-----|
|トポロジで SEFAUtil ツールを有効にする|新しい信頼New-CsTrustedApplicationPoolを作成するには、このコマンドレットを使用します。 SEFAUtil ツールNew-CsTrustedApplication信頼できるアプリケーションとして指定するには、このコマンドレットを使用します。 トポロジを有効にするにはEnable-CsTopologyコマンドレットを実行します。 まだインストールしていない場合は、この場所から Skype for Business Server バージョンの SEFAUtil ツールをダウンロードし、手順 1 で作成した信頼できるアプリケーション プールにインストールします。 SEFAUtil が正しく実行されていることを確認するには、SEFAUtil を実行して、展開内のユーザーの通話転送設定を表示します。 |RTCUniversalServerAdmins  <br/> |[Skype for Business で SEFAUtil ツールを展開する](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Skype for Business Server 2015 リソース キット ツールのドキュメント](../../management-tools/resource-kit-tools.md)。 (Skype for Business Server では、現在のバージョンのツールを使用する必要がありますが、Lync Server 2013 のこのドキュメントは引き続き適用されます)。  <br/> |
|コール パーク オービット テーブルで通話ピックアップ番号範囲を構成する  <br/> |**New-CSCallParkOrbit** コマンドレットを使用して、コール パーク オービット テーブルに通話ピックアップ番号範囲を作成し、コール ピックアップ範囲に **GroupPickup** 型を割り当てる。  <br/> 既存のダイヤル プランとシームレスに統合するには、通常、番号範囲は仮想内線番号のブロックとして構成されます。 コール パーク オービット テーブル内の範囲番号としてダイレクト インワード ダイヤル (DID) 番号を割り当てるのはサポートされていません。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business でグループ通話ピックアップ番号範囲を作成または変更する](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|ユーザーに通話ピックアップ番号を割り当て、ユーザーのグループ通話ピックアップを有効にする  <br/> |SEFAUtil リソース キット ツールの /enablegrouppickup パラメーターを使用して、グループ通話ピックアップを有効にし、ユーザーに通話ピックアップ番号を割り当てる。  <br/> |-  <br/> |[ユーザーのグループ通話ピックアップを有効にし、Skype for Business でグループ番号を割り当てる](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|割り当てられた通話ピックアップ番号とその他の関心のある番号をユーザーに通知する  <br/> |ユーザーのグループ通話ピックアップを有効にした後、電子メールなどのメカニズムを使用して、ユーザーに通話ピックアップ グループ番号を通知します。 ユーザーが監視する可能性がある任意のグループの通話ピックアップ グループ番号をユーザーに通知します。 ユーザーが同じグループにいなくても、他のユーザーの呼び出しを取得できるので、複数のグループに対して通話ピックアップ グループ番号が必要になる場合があります。  <br/> |-  <br/> ||
|グループ通話ピックアップの展開を確認する  <br/> | 呼び出しの配置と取得をテストして、構成が期待した通り動作します。 少なくとも、次の情報を確認します。 <br/>  グループ通話ピックアップが有効になっているユーザーを呼び出し、別のユーザーに呼び出しを取得します。 他のユーザーは、同じグループ、別のグループ、またはグループ通話ピックアップを有効にすることはできません。 <br/>  グループ通話ピックアップが有効で、通話に応答しないユーザーを呼び出します。 <br/> |-  <br/> ||
