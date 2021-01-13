---
title: tblSystemRevision
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 95b8e307-117c-4fb0-bd52-bc5a5b9ade55
description: tblSystemRevision には、複数の管理者クライアント間で一貫性を保つ目的で tblAdminLock テーブルと一緒に使用されるリビジョン番号が含まれている。
ms.openlocfilehash: 5bbcf547d6e6f31cc3e9d71415fed6f351c82910
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831417"
---
# <a name="tblsystemrevision"></a><span data-ttu-id="25052-103">tblSystemRevision</span><span class="sxs-lookup"><span data-stu-id="25052-103">tblSystemRevision</span></span>
 
<span data-ttu-id="25052-104">tblSystemRevision には、複数の管理者クライアント間で一貫性を保つ目的で tblAdminLock テーブルと一緒に使用されるリビジョン番号が含まれている。</span><span class="sxs-lookup"><span data-stu-id="25052-104">tblSystemRevision contains the revision number that is used with the tblAdminLock table to achieve consistency across multiple administrator clients.</span></span>
  
<span data-ttu-id="25052-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="25052-105">**Columns**</span></span>

|<span data-ttu-id="25052-106">**列**</span><span class="sxs-lookup"><span data-stu-id="25052-106">**Column**</span></span>|<span data-ttu-id="25052-107">**型**</span><span class="sxs-lookup"><span data-stu-id="25052-107">**Type**</span></span>|<span data-ttu-id="25052-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="25052-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="25052-109">sysRevision</span><span class="sxs-lookup"><span data-stu-id="25052-109">sysRevision</span></span>  <br/> |<span data-ttu-id="25052-110">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="25052-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="25052-111">改訂番号</span><span class="sxs-lookup"><span data-stu-id="25052-111">Revision number.</span></span>  <br/> |
   

