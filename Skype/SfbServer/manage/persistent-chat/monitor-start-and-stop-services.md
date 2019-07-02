---
title: Skype for Business Server 2015 での常設チャット サービスの監視、開始、および停止
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: '概要: Skype for Business Server 2015 で常設チャットサービスの開始、停止、監視を行う方法について説明します。'
ms.openlocfilehash: 9d2edf0e05a6efcd6e9354696cceade8265abbac
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418692"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット サービスの監視、開始、および停止
 
**概要:** Skype for Business Server 2015 で常設チャットサービスの開始、停止、監視を行う方法について説明します。
  
常設チャットサービスと常設チャットのコンプライアンスサービスは、Skype for Business Server トポロジの一部であり、次のコマンドレットを使用して、監視、停止、開始することができます。
  
|||
|:-----|:-----|
|get-CsWindowsService  <br/> |Windows サービスとして実行される Skype for Business Server 2015 コンポーネントに関する詳細情報を返します。  <br/> |
|start-CsWindowsService  <br/> |サービスを開始します。  <br/> |
|stop-CsWindowsService  <br/> |サービスを停止します。  <br/> |
   
> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。 常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。 

これらのコマンドレットの使用法の詳細については、「[Skype for Business Server 2015 Management Shell](../management-shell.md)」を参照してください。
  

