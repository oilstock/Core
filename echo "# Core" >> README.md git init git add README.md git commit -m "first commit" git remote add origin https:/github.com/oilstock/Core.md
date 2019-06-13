$db = new Model();
			
			$rResult = $db->query($sQuery);

			/* Data set length after filtering */
			$sQuery = "
				SELECT FOUND_ROWS()
			";
			$rResultFilterTotal = $db->query($sQuery);
			$iFilteredTotal = $rResultFilterTotal[0]['FOUND_ROWS()'];

			/* Total data set length */
			$sQuery = "
				SELECT COUNT(".$sIndexColumn.")
				FROM   $sTable
			";
			$rResultTotal = $db->query($sQuery);
			$iTotal = $rResultTotal[0]['COUNT(id)'];
