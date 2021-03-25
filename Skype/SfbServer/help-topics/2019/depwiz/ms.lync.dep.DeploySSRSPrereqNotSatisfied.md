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
ms.openlocfilehash: 657c1b203dd5d01fedde9ad0c5b08c6775f4bd4e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118906"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (前提条件を満たしていない)

このページは、インフラストラクチャに監視サーバーが展開されていない場合に表示されます。監視サーバーのレポートを展開するための最小要件を満たしていないことを示しています。

この問題を解決するには、監視サーバーがドメインに参加し、それがトポロジ ビルダーで定義され、トポロジが公開済みである必要があります。 SQL Serverレポート サービスは、SQL Serverで使用できる必要があります。また、機能として、レポート サーバー上の監視サーバー データベースにインストールSQL Server。

詳細については [、「Install Monitoring Reports in Skype for Business Server」](../../../deploy/deploy-monitoring/install-monitoring-reports.md) および [「Deploying Monitoring」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)。