---
title: Skype for Business Server 2015 での常設チャット サービスの監視、開始、および停止
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: '概要: Skype for Business Server 2015 で常設チャット サービスを開始、停止、監視する方法について学習します。'
ms.openlocfilehash: 31285fe5f7eefaa6579f2891a4b29111324de22d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814137"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット サービスの監視、開始、および停止
 
**概要:** Skype for Business Server 2015 で常設チャット サービスを開始、停止、監視する方法について学習します。
  
常設チャット サービスと常設チャット コンプライアンス サービスは Skype for Business Server トポロジの一部であるため、次のコマンドレットを使用して監視、停止、および開始できます。
  
|||
|:-----|:-----|
|get-CsWindowsService  <br/> |Windows サービスとして実行される Skype for Business Server 2015 コンポーネントに関する詳細情報を戻します。  <br/> |
|start-CsWindowsService  <br/> |サービスを開始します。  <br/> |
|stop-CsWindowsService  <br/> |サービスを停止します。  <br/> |
   
> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。 

コマンドレットの使用方法の詳細については [、「Skype for Business Server 2015 Management Shell」を参照してください](../management-shell.md)。
  

