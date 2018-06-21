---
title: 証明書要求 (テンプレートの指定)
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestTemplate
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d00ed98f-46f2-4367-b34c-513e5eafdd06
description: 代替証明書テンプレートの指定] ページを使用すると、既定で使用されている web サーバー証明書テンプレート] 以外の証明書テンプレートを定義できます。 テンプレートを選択した証明機関の場合は、代替の証明書] チェック ボックスを使うを選択し、テキスト ボックスの証明書テンプレートの名前で別の証明書テンプレートの名前を定義します。 証明機関 (CA) で定義したのと同じテンプレート名を使用する必要があります。 前のページに戻るに戻る] をクリックします。 証明書要求の処理を終了するには [キャンセル] をクリックします。
ms.openlocfilehash: 730992312f13557145ebe88aef757bd0fdf433d8
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "19979933"
---
# <a name="certificate-request-specify-termplate"></a>証明書要求 (テンプレートの指定)
 
[**別の証明書テンプレートの指定**] ページでは、既定で使用される WebServer 証明書テンプレート以外の証明書テンプレートを定義できます。[**選択された証明機関に別の証明書テンプレートを使用する**] チェック ボックスをオンにしてから、[**証明書テンプレート名**] テキスト ボックスで別の証明書テンプレートの名前を定義します。証明機関 (CA) で定義したのと同じテンプレート名を使用する必要があります。前のページに戻るには、[**戻る**] をクリックします。証明書要求プロセスを終了するには、[**キャンセル**] をクリックします。
  
> [!CAUTION]
> このオプションは、証明書を発行するときにパブリック CA のシステムで定義されている特定のテンプレートを使用するようパブリック CA から指示を受けた場合にのみ使用してください。内部 CA が証明書を発行する場合は、CA 管理者が、別の証明書テンプレートに使用する名前について指示します。このオプションは、組織で新しい WebServer テンプレートを定義しており、既定の WebServer テンプレートを無効にしている場合に特に有用です。 
  

