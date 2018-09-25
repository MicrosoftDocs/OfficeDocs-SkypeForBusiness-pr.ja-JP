---
title: (SCCM) では、MSI を使用してマイクロソフトのチームをインストールします。
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/31/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: 管理者は、ユーザーまたはコンピューターを選択するのには、マイクロソフトのチームの dpeloy を一括 (SCCM) を持つチームの msi ファイルを使用できます。
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7db13d34eec5f04a1d73a85bbd4bed4044f3cfc7
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012682"
---
<a name="install-microsoft-teams-using-msi-with-sccm"></a><span data-ttu-id="6f74e-103">(SCCM) では、MSI を使用してマイクロソフトのチームをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6f74e-103">Install Microsoft Teams using MSI (with SCCM)</span></span>
===========================================

<span data-ttu-id="6f74e-104">マイクロソフトでは、ユーザーまたはコンピューターを選択するのにはチームを展開する MSI ファイルを一括管理の提供があります。</span><span class="sxs-lookup"><span data-stu-id="6f74e-104">Microsoft has provided an MSI file for admins to bulk deploy Teams to select users or machines.</span></span> <span data-ttu-id="6f74e-105">管理者は、リモートで展開するチームのユーザーがチームのアプリケーションを手動でダウンロードするのに必要はありません、このファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6f74e-105">Admins can use this file to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="6f74e-106">System Center 構成マネージャー (SCCM) は、管理された展開の MSI ファイルで使用する主要なツールです。</span><span class="sxs-lookup"><span data-stu-id="6f74e-106">System Center Configuration Manager (SCCM) is the primary tool used with MSI files for managed deployments.</span></span>

                                                                               
