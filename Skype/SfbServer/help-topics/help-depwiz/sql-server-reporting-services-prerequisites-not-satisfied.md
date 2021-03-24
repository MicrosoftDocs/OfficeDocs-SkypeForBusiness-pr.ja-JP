---
title: SQL Server Reporting Services (前提条件を満たしていない)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: このページは、インフラストラクチャに監視サーバーが展開されていない場合に表示されます。監視サーバーのレポートを展開するための最小要件を満たしていないことを示しています。
ms.openlocfilehash: 792c9d3b6e7c398d517549eb55aaf85086badb64
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100013"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (前提条件を満たしていない)

このページは、インフラストラクチャに監視サーバーが展開されていない場合に表示されます。監視サーバーのレポートを展開するための最小要件を満たしていないことを示しています。

この問題を解決するには、監視サーバーがドメインに参加し、それがトポロジ ビルダーで定義され、トポロジが公開済みである必要があります。 SQL Serverレポート サービスは、SQL Serverで使用できる必要があります。また、機能として、レポート サーバー上の監視サーバー データベースにインストールSQL Server。

詳細については [、「Install Monitoring Reports in Skype for Business Server 2015」](../../deploy/deploy-monitoring/install-monitoring-reports.md) および [「Deploying Monitoring」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)。