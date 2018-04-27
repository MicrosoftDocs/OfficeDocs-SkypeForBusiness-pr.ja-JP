---
title: (SCCM) では、MSI を使用してマイクロソフトのチームをインストールします。
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/31/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: 管理者は、ユーザーまたはコンピューターを選択するのには、マイクロソフトのチームの dpeloy を一括 (SCCM) を持つチームの msi ファイルを使用できます。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26ccdc54ab8ba60cf3bfb8c147ff2e08e496aa30
ms.sourcegitcommit: 5cc51e2d3898fccd1969accedb5e185a332e83bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2018
---
<a name="install-microsoft-teams-using-msi-with-sccm"></a><span data-ttu-id="50115-103">(SCCM) では、MSI を使用してマイクロソフトのチームをインストールします。</span><span class="sxs-lookup"><span data-stu-id="50115-103">Install Microsoft Teams using MSI (with SCCM)</span></span>
===========================================

<span data-ttu-id="50115-104">マイクロソフトでは、ユーザーまたはコンピューターを選択するのにはチームを展開する MSI ファイルを一括管理の提供があります。</span><span class="sxs-lookup"><span data-stu-id="50115-104">Microsoft has provided an MSI file for admins to bulk deploy Teams to select users or machines.</span></span> <span data-ttu-id="50115-105">管理者は、リモートで展開するチームのユーザーがチームのアプリケーションを手動でダウンロードするのに必要はありません、このファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="50115-105">Admins can use this file to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="50115-106">System Center 構成マネージャー (SCCM) は、管理された展開の MSI ファイルで使用する主要なツールです。</span><span class="sxs-lookup"><span data-stu-id="50115-106">System Center Configuration Manager (SCCM) is the primary tool used with MSI files for managed deployments.</span></span>

                                                                               
