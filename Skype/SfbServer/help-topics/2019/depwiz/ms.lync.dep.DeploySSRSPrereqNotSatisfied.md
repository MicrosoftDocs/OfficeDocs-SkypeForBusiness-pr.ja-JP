---
title: SQL Server Reporting Services (前提条件を満たしていない)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
ROBOTS: NOINDEX, NOFOLLOW
description: このページは、インフラストラクチャに監視サーバーが展開されていない場合に表示されます。監視サーバーのレポートを展開するための最小要件を満たしていないことを示しています。
ms.openlocfilehash: 291a6926e632c488d4a51049a9a7bee9d0cde414846c4542ca5559e80c7ed91a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307728"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (前提条件を満たしていない)

このページは、インフラストラクチャに監視サーバーが展開されていない場合に表示されます。監視サーバーのレポートを展開するための最小要件を満たしていないことを示しています。

この問題を解決するには、監視サーバーがドメインに参加し、それがトポロジ ビルダーで定義され、トポロジが公開済みである必要があります。 SQL Server Reporting Servicesで使用可能で、SQL Serverの監視サーバー データベースに機能としてインストールする必要SQL Server。

詳細については、「Install Monitoring Reports in [Skype for Business Server」](../../../deploy/deploy-monitoring/install-monitoring-reports.md)および[「Deploying Monitoring」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)。