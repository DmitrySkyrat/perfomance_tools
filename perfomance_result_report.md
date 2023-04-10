# Performance report

1. Compression optimization:
   - Added compression to `server.js`
   ```javascript
   const compression = require('compression');
   app.use(compression());
   app.use(express.static('build'));
   ```
   - `bundle.js` includes a `content-encoding: gzip` header'.

2.  Image optimizations:
   - In `src/model.js` replaced `const dir = 'big'` with `const dir = 'small'`.
   - Total score was increased and page loads faster (perfomance score 42).

3. `Eliminate render-blocking resources` fix:
   - Deleted `<script src="/libs/lodash.js">` and `<script src="/libs/jquery.js"></script>`
   in `template.html`.

4. `Minimize main-thread work` fix:
   - Changed `"mode":"development"` to `"mode":"production"` in `webpack.config.js`.
   - Total perfomance score was increased to 80.
   - Commented `this.mineBitcoin(1500)` call in the `constructor`.
   - Total perfomance score was increased to 97.