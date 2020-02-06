---
title: レジストラー設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: 回復性は、レジストラープールの高可用性と障害回復機能を提供します。 プライマリレジストラーの障害が発生した場合にバックアップレジストラーを提供することによって、バックアップレジストラーは、失敗したレジストラーを引き継ぐことができるため、ユーザーはログオンして通信することができます。 ユーザーは、プライマリレジストラーで障害が発生したシステムによっては、機能が制限される可能性があります。
ms.openlocfilehash: c603310e6b99721aace04c4e596989fc394ef0ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819329"
---
# <a name="registrar-settings-expander"></a>レジストラー設定エキスパンダー
 
回復性は、レジストラープールの高可用性と障害回復機能を提供します。 プライマリレジストラーの障害が発生した場合にバックアップレジストラーを提供することによって、バックアップレジストラーは、失敗したレジストラーを引き継ぐことができるため、ユーザーはログオンして通信することができます。 ユーザーは、プライマリレジストラーで障害が発生したシステムによっては、機能が制限される可能性があります。
  
Survivable Branch Appliance または Survivable Branch Server の [**プロパティの編集**] ダイアログボックスの [**回復性**] セクションで、次の設定を変更できます。
  
- **関連付けられているユーザーサービスとバックアップレジストラープール**ドロップダウンリストで、Survivable Branch Appliance または Survivable Branch Server のバックアップレジストラーとして機能する Enterprise Edition フロントエンドプールまたは Standard Edition フロントエンドサーバーを選びます。
    
- **フェールオーバーとフェールバックを有効にする**この設定を選択すると、失敗したレジストラーが自動検出され、プライマリレジストラーがバックアップされ、レジストラープロセスを再開する準備ができたことが自動判断されます。
    
- **失敗検出の間隔 (秒)** プライマリレジストラーが失敗したと判断されるまでの時間 (秒数) を入力します。 既定値は120秒です。 [**フェールオーバーとフェールバックを有効に**する] を選択した場合、このフィールドは必須です。
    
- **フォールバック検出の間隔 (秒)** プライマリレジストラーがバックアップされたことを確認するまでの時間 (秒数) を入力します。 既定値は240秒です。 [**フェールオーバーとフォールバックを有効に**する] を選択した場合、このフィールドは必須です。
    
> [!IMPORTANT]
> 障害検出間隔とフォールバック検出間隔を定義した場合、レジストラーが短時間応答しない場合は、フェールオーバーとフォールバックが発生する間隔を入力しないように注意してください。 プールまたはサーバーの読み込みに基づいて、プライマリレジストラーが短時間応答しない可能性があります。 
  

