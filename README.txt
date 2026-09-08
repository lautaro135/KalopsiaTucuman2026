1) Ejecutá supabase.sql en Supabase > SQL Editor.
   - Si ya tenías la base creada antes, no pasa nada: el script usa "if not exists" / "add column if not exists",
     así que podés volver a correrlo tranquilo y solo va a agregar las columnas nuevas
     (codigo_barras, es_combo, combo_items) a la tabla productos.
2) En index.html reemplazá SUPABASE_URL y SUPABASE_KEY (si ya estaban cargadas, dejalas como están).
3) Subí la carpeta a GitHub y conectala con Netlify, o arrastrala a Netlify.
IMPORTANTE: las policies demo son públicas; para una app real con usuarios hay que agregar Supabase Auth y RLS por negocio.

NOVEDADES DE ESTA VERSIÓN:
- Código de barras: en "Vender" hay un campo para escanear y sumar el producto al ticket automáticamente.
  En "Productos" hay un campo para escanear y sumar stock a un producto existente, y el formulario de
  alta/edición de producto tiene un campo "Código de barras" para asignarlo al cargarlo al sistema.
  Cualquier lector de código de barras USB/Bluetooth funciona (se comporta como un teclado que escribe
  el código y aprieta Enter).
- Combos/promos: botón "Nuevo combo/promo" en Productos. Armás el combo eligiendo productos base y
  cantidades (ej: 3x Jean). El stock del combo se calcula solo, en base al stock disponible de sus
  componentes, y al cobrar una venta con el combo se descuenta automáticamente la cantidad correspondiente
  de cada producto base (ej: vender 1 "Promo 3 jeans" descuenta 3 unidades del stock de "Jean").
