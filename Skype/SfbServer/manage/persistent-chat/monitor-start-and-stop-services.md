---
title: 2015 年の常設チャット サービスの監視、開始、および停止Skype for Business Server。
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: '概要: 2015 年に常設チャット サービスを開始、停止、監視するSkype for Business Serverします。'
ms.openlocfilehash: f2b2c964659b3de5045d414736bc5c1e5ddadd28
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766485"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>2015 年の常設チャット サービスの監視、開始、および停止Skype for Business Server。
 
**概要:** 2015 年に常設チャット サービスを開始、停止、監視するSkype for Business Serverします。
  
常設チャット サービスと常設チャット コンプライアンス サービスは Skype for Business Server トポロジの一部であるため、次のコマンドレットを使用して監視、停止、および開始できます。
  
|コマンドレット|職務|
|:-----|:-----|
|get-CsWindowsService  <br/> |サービスとして実行される 2015 Skype for Business Serverの詳細な情報をWindowsします。  <br/> |
|start-CsWindowsService  <br/> |サービスを開始します。  <br/> |
|stop-CsWindowsService  <br/> |サービスを停止します。  <br/> |
   
> [!NOTE]
> 常設チャットは 2015 Skype for Business Serverで使用できますが、2019 年Skype for Business Serverではサポートされていません。 同じ機能は、Teams。 詳細については、「アップグレードの開始[方法」をMicrosoft Teamsしてください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、2015 年Skype for Business Serverします。 

コマンドレットの使用方法の詳細については、「Skype for Business Server [2015 管理シェル」を参照してください](../management-shell.md)。
  

